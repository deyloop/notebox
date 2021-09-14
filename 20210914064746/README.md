# Creating a GPG key

The `gpg` tool needs to be installed.

1. Generate GPG key pair.

       gpg --full-generate-key

1. Specify the kind of key
1. Specify key size. (Github mandates higher than 4096 bits)
1. Enter length of validity. (2y is a good one)

   > ⚠️ 
   > Never use a key that never expires. This helps in the case the private key is
   > lost, you will be assured that the public key will at least expire some-day, so
   > you stop receiving messages encrypted using the lost key.  

1. Enter identifying information like name, email and comment.
1. Select a passphrase.
1. Upload the key to public key servers

       gpg --send-keys <key-id>

   where you can get your key id using
   
       gpg --list-keys


References:
* <https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification/generating-a-new-gpg-key>
