# Increase timeout for GPG passphrase cache

* GPG agents require a passphrase to unlock gpg signatures. This passphrase is
  cached for  subsequent signings. This cache has a timeout / ttl.
* By default this ttl is around 5 minutes. This can be annoying if you [sign
  your git commits][1] and make many small commits throughout the day, as you
  will be required to enter the passphrase every so often.

The cache ttl can be set in `~/.gnupg/gpg-agent.conf`:

```
default-cache-ttl 34560000
max-cache-ttl 34560000
```

> ⚠️ Take caution on setting a ttl that is too long if you are in a shared
> system or are in an area where you suspect someone might snoop on your
> computer.

[1]: ../20210914072507/README.md

Related:

* [20210914072507](../20210914072507/README.md) Sign git commits with GPG
* [20210914062938](../20210914062938/README.md) Pretty Good Privacy (PGP)

Tags:

    #literature-note #security

