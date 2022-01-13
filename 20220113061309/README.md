# Increase timeout for GPG passphrase cache

* GPG agents require a passphrase to unlock gpg signatures. This passphrase is
  cached for  subsequent signings. This cache has a timeout / TTL.
* By default this TTL is around 10 minutes of no GnuPG activity (resets if you
  use it), and a max TTL of 2 hours. This can be annoying if you [sign your git
  commits][1] and make many small commits throughout the day, as you will be
  required to enter the passphrase every so often.

The cache TTL can be set in `~/.gnupg/gpg-agent.conf`:

```
default-cache-ttl 34560000
max-cache-ttl 34560000
```

The values are in seconds. This sets both TTLs to 400 days (just over a year)

> ⚠️ Take caution on setting a TTL that is too long if you are in a shared
> system or are in an area where you suspect someone might snoop on your
> computer.

I personally use values of 6hrs and 1 Day for both of these respectively.

[1]: ../20210914072507/README.md

Related:

* [20210914072507](../20210914072507/README.md) Sign git commits with GPG
* [20210914062938](../20210914062938/README.md) Pretty Good Privacy (PGP)

Tags:

    #literature-note #security

