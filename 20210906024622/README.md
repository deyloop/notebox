# `timedatectl` to control system time on linux

The `timedatectl` command can be used to set the time-zone and other date and
time settings from the command-line in linux (or at least in arch linux)

`timedatectl` is part of the `systemd` suit of programs.

Description from the *`systemd` man page*:

  `timedatectl` may be used to query and change the system clock and its
  settings, and enable or disable time synchronization services.

To check time information:

```sh
timedatectl status
```

**output**

                 Local time: Mon 2021-09-06 08:29:05 IST
             Universal time: Mon 2021-09-06 02:59:05 UTC
                   RTC time: Mon 2021-09-06 02:59:05
                  Time zone: Asia/Kolkata (IST, +0530)
  System clock synchronized: yes
                NTP service: active
            RTC in local TZ: no


To set the time manually:

```sh
# time format: YYYY-MM-DD HH:MM:SS
timedatectl set-time "2021-09-06 08:25:26"
```

To set the time zone:

```sh
# setting to IST (Asia/Kolkata)
timedatectl set-timezone Asia/Kolkata
```

You can also look at what time-zones are available:

```sh
timedatectl list-timezones
```

**References**
* <https://www.archlinuxuser.com/2013/01/how-to-set-local-time-on-archlinux.html>
* <https://www.freedesktop.org/software/systemd/man/timedatectl.html>
