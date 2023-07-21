# Cheat sheet #3


## Copy Ubuntu iso to a usb drive to boot on a computer.
(macOs)

`cd ~/Downloads`

`diskutil list`

`diskutil unmountDisk /dev/diskX`

`sudo dd if=ubuntu-XX.XX-desktop-amd64.iso of=/dev/diskX bs=1m`

