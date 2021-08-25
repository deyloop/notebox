# Fixing Windows Boot-loader not showing up in `grub`

After installing linux alongside Windows, some distributions like Ubuntu and
EndevourOS, Windows does not show up in the grub menu. 

This is because by default, Grub no longer calls `os-prober`, a tool used to
check what other operating systems are installed alongside Linux. 

A quick fix for this is:
1. Edit the grub configuration

```sh
sudo vim /etc/default/grub
```

  and make sure to have `GRUB_DISABLE_OS_PROBER=false` in the file.

2. Update Grub configuration using

```sh
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

Windows showed up in the next boot, at least for me.

**Note**: Do make sure that the partition/drive that contains the boot/efi for
Windows is mounted when running `grub-mkconfig`.

#### References

<https://www.reddit.com/r/EndeavourOS/comments/oevlfo/windows_boot_option_not_showing_after_i_installed/>
