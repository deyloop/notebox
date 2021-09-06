# Setting up Printer and Scanning in Linux

I had to set up printer and scanning on EndevourOS. This should be for all arch
distros. This note describes the steps that I followed. I have an HP Deskjet
Printer and scanner.

## Setup

The `hplip` package is all that is needed to set up printing using a HP
printer. It has a couple perl and python dependencies, along with a dependency
on a package called `cups` that I had to add separately 

```sh
yay -S cups hplip
sudo systemctl enable --now cups
```

After this I used the interactive setup utility, with my printer attached on a
USB port.

```sh
sudo hp-setup -i
```

An optional GUI for managing printers can also be installed

```sh
yay -S system-config-printer
```

> ℹ️
> This seems to be a python script


After this the Printer was available for printing.

## Scanning

The `hplip` package contains the `hp-scan` tool, but a few python dependencies
were missing.

Installing these python packages fixed the issues.

```sh
yay -S xsane python-pillow python-reportlab
```

After this, the scanned documents can be saved as pdf using something like this:

```sh
hp-scan -i -oBill-1.pdf --dest=pdf
```

**References**
* <https://unix.stackexchange.com/a/392629>
* <https://manpages.ubuntu.com/manpages/trusty/man1/hp-scan.1.html>
