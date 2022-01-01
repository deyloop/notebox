# X Clipboards

X has a things called "selections" which are just clipboards.

There are 3 selections one needs to be aware of:

* `PRIMARY` for mouse selections. This is where terminal emulators, for
  example, will put stuff that gets selected, so this usually contains text
  that was last selected/highlighted with a mouse. This content can usually be
  accessed using middle mouse button.

  This does means that selecting anything overwrites this clipboard.

* `SECONDARY` - from the Arch Wiki:

  > SECONDARY is only used inconsistently and was intended as an alternate to
  > PRIMARY. 

  It is just another option, no one uses it in particular

* `CLIPBOARD` for Windows-style cut/copy/paste (explicitly pressing Ctrl-C
  after selection, for example). 


References:

* ArchWiki - Clipboard: <https://wiki.archlinux.org/title/Clipboard#content>

Related:

* `xclip` tool
* `xsel` tool

Tags:

  #literature-note #linux #X11

