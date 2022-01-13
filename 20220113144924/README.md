# How I Remap my Keys

* `CAPSLOCK` is `Left-Ctrl`
* `Left-Ctrl` (and my substitution `CAPSLOCK`) is `Esc` when tapped, `Ctrl`
  when pressed with other keys. (`Ctrl+A`, for example)

This is achieved using the following commands, which are run on startup.

```sh
# Remaps Left Control to Escape
xcape -e 'Control_L=Escape'
```

and

```sh
# Remaps the CapsLock to Ctrl
/usr/bin/setxkbmap -option "ctrl:nocaps"
```

Related:

* My dotfiles <https://github.com/deyloop/dot>

Tags:

    #permanent-note #linux #personalisation #tips
