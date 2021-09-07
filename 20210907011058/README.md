# `reflector` for Updating `pacman` mirror-list

`pacman`'s mirror-list needs to be updated/reordered if move large distances
across the world, so that `pacman` can pull packages from the fastest mirrors
available in the current area.

The `reflector` utility can be used to pull an updated mirror list from the
Arch Mirror Status page (<https://www.archlinux.org/mirrors/status/>).

I used the following to update the mirror list:

```sh
sudo reflector --verbose --latest 10 --protocol https --sort rate --save /etc/pacman.d/mirrorlist
```


