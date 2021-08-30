# Enabling Bluetooth on EndevourOS/Arch

EndevourOS does not have Bluetooth enabled by default.

Here are the steps to get it working:

```sh
# install the bluetooth packages
sudo pacman -S --needed bluez bluez-utils pulseaudio-bluetooth blueman

# restart pulseaudio so that the bluetooth module is loaded
pulseaudio -k
```

Subsequently, to use Bluetooth,

```sh
# start the bluetooth daemon
sudo systemctl start bluetooth

# Use blueman to select bluetooth devices to connect to
blueman-manager
```

References:

* [Enable and Setup Bluetooth devices - EndevourOS Wiki](https://discovery.endeavouros.com/bluetooth/bluetooth/2021/03/)
* [Bluetooth - ArchWiki](https://wiki.archlinux.org/title/Bluetooth)
