---
comments: true
date: 2013-07-23
layout: post
title: Ensure Complete Data Protection With Encrypted Forms
published: true
---

## Encrypted forms

We are excited to add support for encrypted forms to Formhub.  Encrypted forms work by encrypting the data on the phone the moment it is saved.  Data sent to formhub is encrypted and completely inaccessible to anyone not possessing the private key.  In this case,  Formhub serves simply as a storage locker for your encrypted files - a place to upload and then download for later for local decryption ([using ODK Briefcase](http://blog.formhub.org/2013/06/27/formhub-supports-odk-briefcase/)).   Since the form submissions are encrypted, it means, however, anything that requires access to the data like the map view or data export won't work within Formhub.  The extra level of security makes using Formhub in a way to collect sensitive data while meeting IRB protocols possible.  This has been a major request from our University colleagues so we are particularly excited to announce support for this important feature.

## How it Works?

ODK Collect supports the ability to encrypt the content of a form the moment it is marked as completed and ready for submission on the phone.  To take advantage of this requires the use of a public encryption key which you include in the XLSForm and a private key (which you never share) that is used by ODK Briefcase to decrypt the data locally after you've downloaded it from Formhub.  The public key is used to encrypt data while the private key decrypts it. Only a person who has the private key, can decrypt the data encrypted with the public key.  To understand more about public and private key infrastructure see [http://en.wikipedia.org/wiki/Public-key_cryptography/ ](http://en.wikipedia.org/wiki/Public-key_cryptography/ ).

## How to encrypt XLS forms

1. In your XLSform, add a worksheet called *'settings'*
1. In this worksheet create three columns namely: *' id_string'*,
   *'submission_url'*  (is your submission url),  and *'public_key'*  (is the
   base64RsaPublicKey). See below for more information on generating the required public key. Do not set a password when generating the key. The public key is the key that is on the 'public_key' column on the 'settings' worksheet of your xlsform. The syntax for the form is as shown by the image below:
![](http://farm6.staticflickr.com/5449/9236043481_06a3e98257_o.png)
1. Upload the xlsform to formhub as usual. You should see a label with the text
  "encrypted" next to your form name on formhub as shown below:
  ![](http://farm6.staticflickr.com/5462/9302350574_d323840bef_o.png)


<!--more-->


## How to decrypt forms?

ODK Briefcase (see earlier post) is used to download the encrypted files from Formhub and decrypt them locally on your computer using a private key ensuring single access to the data. For decryption to be successful with ODK Briefcase  make sure you install Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files 6 from this [site](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

1. Open ODK Briefcase.
1. PULL the encrypted form  to your PC. See how to PULL forms from formhub in our
   previous post [Formhub now supports ODK briefcase](http://blog.formhub.org/2013/06/27/formhub-supports-odk-briefcase/)
1. The encrypted form is decrypted only during export. Go to the 'Export Tab' and
   specify the PEM private key to decrypt the form.

   ![](http://farm3.staticflickr.com/2883/9238828660_b9353b9e51_o.png)
1. Click 'Export'
1. Data is exported as a CSV file, you can now be able to view the unencrypted
   data.

## Generating RSA Encryption Keys

To generate the Rsa public-private key pairs  you can use the OpenSSL software package, which is pre-installed on OSX and Linux. On Windows you have to download and install the OpenSSL software package from this [site](http://slproweb.com/products/Win32OpenSSL.html).

**How to generate rsa key for use with encrypted forms on formhub**

1. Open a Windows 'cmd' window.
1. Type the following command: _cd C:\OpenSSL-Win32\bin_ to change to the /bin directory in the OpenSSL directory.
![](http://farm8.staticflickr.com/7290/9915295964_70b9ec8114_o.png)
1. Create a 2048-bit private key and write it to the **MyPrivateKey.pem** file by typing the following command, then press **Enter**:
_openssl genpkey -out MyPrivateKey.pem -outform PEM -algorithm RSA -pkeyopt rsa_keygen_bits:2048_
![](http://farm8.staticflickr.com/7309/9915249576_a8994127af_o.png)
1. Then, extract the public key for the above private key. Type the following command then press **Enter**:
_openssl rsa -in MyPrivateKey.pem -inform PEM -out MyPublicKey.pem -outform PEM -pubout_
![](http://farm8.staticflickr.com/7309/9915249576_a8994127af_o.png)
1. You have now generated two files that is:
  - **MyPrivateKey.pem** - your private key that you need to move to a secure location.
  - **MyPublicKey.pem** - your public key, that you can share with anyone you want to share information securely
1. Open the **MyPublicKey.pem** with notepad, your public key is the uninterrupted very long string of characters e.g _Tjhfur1K9+BRQ2USezIPbtyahbfuNqviI5Suhm8maA3JoELRHj9psjf/oNWoG87aFtKNbLrRaCEDPoFMDC9NEzWlv5L49BygeieMu/wg/rtMT0M0kgDbKxw5weJJgyb9P41aMsrqAAAAB3NzaC1yc2EAAAADAQABAAABAQDfNoFX7bh3bfdW6lGfDht1Ea8PUBLKYjugbHN5jS7j5fHV6dexM+kzvITVgoyjhhKPXeCbaT62vD/saTqJFXJzlysnZ24fqxNkjreO5K5EQ9c3ggwqML06+AKrFUSP5jpnyJJH8btNwKl6D5pG4ZseHwDUKzZtaextPTNQz67kdYIKdtCkCsQHVsy4xvy/A0jzfK3xyOkG6j+L_, this is what you will paste under the public_key field in your settings sheet on your xlsform.
1. **MyPrivateKey.pem** is the file you will use when exporting the submissions using ODK Briefcase.
