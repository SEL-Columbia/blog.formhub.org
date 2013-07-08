## Encrypted forms

We are excited to add support for encrypted forms to Formhub. Encrypted forms work by encrypting the data on the phone the moment it is saved. Data sent to formhub is encrypted and completely inaccessible to anyone not possessing the private key.  In this situation, Formhub serves as simply as a storage locker for your encrypted files. A place to upload and then download for later for local decryption (using ODK Briefcase).   Since the form submissions are encrypted, it means things like the map view won’t work.  However, the extra level of security makes using Formhub in a way to collect sensitive data while meeting IRB protocols possible. This has been a major request from our University colleagues so we are particularly excited to announce support for this important feature.

## How it Works?

Encryption is a way of disguising data in such a way as to hide its content. ODK Collect provides support for asymmetric keys which are composed of a pair of encryption keys. The two keys used for encryption are: **public** and **private** keys.
The public key is used to encrypt data while the private key decrypts it. Only a person who has the private key, can decrypt the data encrypted with the public key. The private key will only be used for decryption by ODK briefcase.

**How to encrypt XLS forms**

1. In your XLSform, add a worksheet called __'settings'__
*  In this worksheet create three columns namely: __‘ id_string’__, 
   __‘submission_url’__ (is your submission url),  and __‘public_key’__ (is the 
   base64RsaPublicKey). See  [http://opendatakit.org/help/encrypted-forms/ ](http://opendatakit.org/help/encrypted-forms/ ). Do not put a password on the key.









