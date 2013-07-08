## Encrypted forms

We are excited to add support for encrypted forms to Formhub. Encrypted forms work by encrypting the data on the phone the moment it is saved. Data sent to formhub is encrypted and completely inaccessible to anyone not possessing the private key.  In this situation, Formhub serves as simply as a storage locker for your encrypted files. A place to upload and then download for later for local decryption (using ODK Briefcase).   Since the form submissions are encrypted, it means things like the map view won’t work.  However, the extra level of security makes using Formhub in a way to collect sensitive data while meeting IRB protocols possible. This has been a major request from our University colleagues so we are particularly excited to announce support for this important feature.

## How it Works?

Encryption is a way of disguising data in such a way as to hide its content. ODK Collect provides support for asymmetric keys which are composed of a pair of encryption keys. The two keys used for encryption are: **public** and **private** keys.
The public key is used to encrypt data while the private key decrypts it. Only a person who has the private key, can decrypt the data encrypted with the public key. The private key will only be used for decryption by ODK briefcase.

**How to encrypt XLS forms**

1. In your XLSform, add a worksheet called *'settings'*
*  In this worksheet create three columns namely: *‘ id_string’*, 
   *‘submission_url’*  (is your submission url),  and *‘public_key’*  (is the 
   base64RsaPublicKey). See  [http://opendatakit.org/help/encrypted-forms/ ](http://opendatakit.org/help/encrypted-forms/ ). Do not put a password on the key.
The two keys are a pair; each public key can only be decrypted by its own corresponding private key. The public key is the key that is on the ‘public_key’ column on the ‘settings’ worksheet of your xlsform.  The public key is openly available.
The public key can be shared with others but the private key should be kept secret, never to be shared, keep it safe and secure. If anyone has access to your private key they can easily have access to your encrypted data.
The syntax for the form is as shown by the image below:
![](http://farm6.staticflickr.com/5449/9236043481_06a3e98257_o.png)
*  Upload the xlsform to formhub as usual.

<!--more-->

**How to decrypt forms?**

ODK Briefcase (see earlier post) is used to download the encrypted files from Formhub and decrypt them locally on your computer using a private key ensuring single access to the data.  

1. Open ODK Briefcase.
*  PULL the encrypted form  to your PC. See how to PULL forms from formhub in our
   previous post [Formhub now supports ODK briefcase](http://blog.formhub.org/2013/06/27/formhub-supports-odk-briefcase/)
*  The encrypted form is decrypted only during export. Go to the ‘Export Tab’ and
   specify the PEM private key to decrypt the form.
![](http://farm3.staticflickr.com/2883/9238828660_b9353b9e51_o.png)

   














