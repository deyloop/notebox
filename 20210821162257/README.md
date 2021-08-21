# Making XMonad Conform to the XDG Base Directory Specification

By default, XMonad's documentation and most tutorials about installing
XMonad and configuring it make use of the `~/.xmonad` directory for config files.

Doing this does not conform to the [XDG Base Directoy Specification] set by
freedesktop.org.

However, since version `0.15`, XMonad does support the specification, but
it requires that the corresponding folders be present.

1. Config files in `$XDG_CONFIG_HOME/xmonad`. `xmonad.hs` should be shifted here.
1. `$XDG_DATA_HOME/xmonad` be present. This is were XMonad places its
   built binary (`xmonad-x86_64-linux` in my case).

Therefore, creating both these directories manually, especially the
second one when setting up XMonad is necessary if it is desired that it
conform to the guidelines. 

References: 
<https://github.com/xmonad/xmonad/issues/148#issuecomment-422563425>
<https://wiki.archlinux.org/title/XDG_Base_Directory#Support>

[XDG Base Directory Specification]: <https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html>
