# Copying to Clipboard from WSL2

`xclip` does not work on WSL2. Instead all content that needs to be accessed
int the clipboard on Windows side needs to go through `clip.exe`.

```sh
cat report.txt | clip.exe
```

References:

* <https://www.raymondcamden.com/2017/10/19/copying-to-clipboard-with-windows-subsystem-for-linux/>
