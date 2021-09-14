# Concurrent Downloads with `pacman`

`pacman` supports downloading packages in parallel **since version 6**, but
this needs to be configured to be enabled. 

Parallel should be enabled if you have a multi-core CPU and want your downloads
and updates to be faster.

Check `pacman` version:
```sh
pacman -V
```
*output*:
```

 .--.                  Pacman v6.0.1 - libalpm v13.0.1
/ _.-' .-.  .-.  .-.   Copyright (C) 2006-2021 Pacman Development Team
\  '-. '-'  '-'  '-'   Copyright (C) 2002-2006 Judd Vinet
 '--'
                       This program may be freely redistributed under
                       the terms of the GNU General Public License.

```

The `pacman` config file is located at `/etc/pacman.conf`. The option that
needs to be added is `ParallelDownloads = 5`. (use a number that suites your
computer, 5 is supposedly the default, says the blog post I referred to.)

References:
* <https://ostechnix.com/enable-parallel-downloading-in-pacman-in-arch-linux/>
