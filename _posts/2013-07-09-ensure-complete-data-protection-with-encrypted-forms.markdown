---  
comments: true  
date: 2013-07-23  
layout: post  
title: Ensure Complete Data Protection With Encrypted Forms  
---

## Encrypted forms

We are excited to add support for encrypted forms to Formhub.  Encrypted forms work by encrypting the data on the phone the moment it is saved.  Data sent to formhub is encrypted and completely inaccessible to anyone not possessing the private key.  In this case,  Formhub serves simply as a storage locker for your encrypted files - a place to upload and then download for later for local decryption ([using ODK Briefcase](http://blog.formhub.org/2013/06/27/formhub-supports-odk-briefcase/)).   Since the form submissions are encrypted, it means, however, anything that requires access to the data like the map view or data export won’t work within Formhub.  The extra level of security makes using Formhub in a way to collect sensitive data while meeting IRB protocols possible.  This has been a major request from our University colleagues so we are particularly excited to announce support for this important feature.

## How it Works?

ODK Collect supports the ability to encrypt the content of a form the moment it is marked as completed and ready for submission on the phone.  To take advantage of this requires the use of a public encryption key which you include in the XLSForm and a private key (which you never share) that is used by ODK Briefcase to decrypt the data locally after you’ve downloaded it from Formhub.  The public key is used to encrypt data while the private key decrypts it. Only a person who has the private key, can decrypt the data encrypted with the public key.  To understand more about public and private key infrastructure see [http://en.wikipedia.org/wiki/Public-key_cryptography/ ](http://en.wikipedia.org/wiki/Public-key_cryptography/ ).

## How to encrypt XLS forms

1. In your XLSform, add a worksheet called *'settings'*
1. In this worksheet create three columns namely: *‘ id_string’*, 
   *‘submission_url’*  (is your submission url),  and *‘public_key’*  (is the 
   base64RsaPublicKey). See below for more information on generating the required public key. Do not set a password when generating the key. The public key is the key that is on the ‘public_key’ column on the ‘settings’ worksheet of your xlsform. The syntax for the form is as shown by the image below:
![](http://farm6.staticflickr.com/5449/9236043481_06a3e98257_o.png)
1. Upload the xlsform to formhub as usual. You should see a label with the text
  “encrypted” next to your form name on formhub as shown below:
  ![](http://farm6.staticflickr.com/5462/9302350574_d323840bef_o.png)
  
  
<!--more-->


## How to decrypt forms?

ODK Briefcase (see earlier post) is used to download the encrypted files from Formhub and decrypt them locally on your computer using a private key ensuring single access to the data.  

1. Open ODK Briefcase.
1. PULL the encrypted form  to your PC. See how to PULL forms from formhub in our
   previous post [Formhub now supports ODK briefcase](http://blog.formhub.org/2013/06/27/formhub-supports-odk-briefcase/)
1. The encrypted form is decrypted only during export. Go to the ‘Export Tab’ and
   specify the PEM private key to decrypt the form.
   
   ![](http://farm3.staticflickr.com/2883/9238828660_b9353b9e51_o.png)
1. Click 'Export’
1. Data is exported as a CSV file, you can now be able to view the unencrypted
   data.  
   
## Generating RSA Encryption Keys

**Windows**

You can use the OpenSSL software package for windows users as described under the section ‘Constructing the RSA Key Pair’ in [http://opendatakit.org/help/encrypted-forms/](http://opendatakit.org/help/encrypted-forms/)

For linux and OSX users, a key pair can be generated using the ssh-keygen command from the terminal.

**How to generate rsa key for use with encrypted forms on formhub**

Even though the steps described below were done on windows, the same exact commands can be used on OSX or linux terminals.

You will need to download git for windows and notepad++ and install them:

1. Download git for windows from [http://git-scm.com/download/win]( http://git-scm.com/download/win)
1. Download notepad++ from [http://notepad-plus-plus.org/download](http://notepad-plus-plus.org/download)


**Steps**

1. Open Git Bash and type the following command then press 
   **Enter**: *ssh-keygen -t rsa -C your_email_address_here*
![](http://farm4.staticflickr.com/3736/9297729067_0b6e32ae63_o.png)
1. You will see a prompt to type the key filename, type *mykey.pem*, then **Enter**:
![](http://farm8.staticflickr.com/7358/9300514536_1b6086cee8_o.png)
1. You will be prompted to enter a passphrase, just press **Enter**: to use a blank
   passphrase.
![](http://farm6.staticflickr.com/5479/9297731635_0949698695_o.png)
1. Another prompt to confirm the passphrase, just press **Enter**:
![](http://farm8.staticflickr.com/7428/9297732469_935c89fe63_o.png)
1. Two files will be generated: to list the files type the **ls** command 
   below:
   
   *ls mykey.pem*
   
   *mykey.pem*; is your private key that you need to keep secure and private
   
   *mykey.pem.pub*; is your public key, that you can share with anyone you want 
      to share information securely
![](http://farm4.staticflickr.com/3744/9300517760_3aa0b59312_o.png)
1. Open Windows Explorer on your home folder you should see the two files above - due
   to file extension hidden settings *mykey.pem.pub* will seem named *mykey.pem* 
   but it may have a Microsoft Publisher logo. rename it to *mypubkey.pub*.
![](http://farm8.staticflickr.com/7384/9307148870_f720ae9e41_o.png)
1. Right click on mypubkey.pub and open with notepad++, your public key is the 
   uninterrupted very long string of characters e.g *AAAAB3NzaC1yc2EAAAADAQABAAABAQDfNoFX7bh3bfdW6Tjhfur1K9+BRQ2USezIPbtyahbfuNqviI5Suhm8maA3JoELRHj9psjf/oNWoG87aFtKNbLrRaCEDPoFMDC9NEzWlv5L49BygeieMu/wg/rtMT0M0kgDbKxw5weJJgyb9P41aMsrqlGfDht1Ea8PUBLKYjugbHN5jS7j5fHV6dexM+kzvITVgoyjhhKPXeCbaT62vD/saTqJFXJzlysnZ24fqxNkjreO5K5EQ9c3ggwqML06+AKrFUSP5jpnyJJH8btNwKl6D5pG4ZseHwDUKzZtaextPTNQz67kdYIKdtCkCsQHVsy4xvy/A0jzfK3xyOkG6j+L*, this is what you will paste under the public_key field in your settings sheet.
1. *mykey.pem* is the file you will use when exporting the submissions using ODK 
   Briefcase.



  


   
   

   
   







   
   

   














