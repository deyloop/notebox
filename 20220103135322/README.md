# Transferring GPG Keys to a new machine

It is recommended that the transfer take place over ssh. Keys can be spoofed
and cracked if done via USB devices, in case the device gets lost.

Transferring the whole Keyring, from the receiving machine:

```sh
scp -rp user@othermachine:/home/user/.gnupg ~/
```

if just one key needs to be transferred:

If you're on the machine that already has the key:

```sh
gpg -export-secret-key SOMEKEYID | ssh othermachine gpg --import
```

If you're on the machine that needs the key:

```sh
ssh othermachine gpg --export-secret-key SOMEKEYID | gpg --import
```


Reference:

* StackOverflow - encryption - How to transfer pgp private key to another computer? <https://stackoverflow.com/questions/3174537/how-to-transfer-pgp-private-key-to-another-computer>


Tags:

    #literature-note #pgp #encryption #security
