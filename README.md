# linux-0.11

A slightly modeified version of linux-0.11 that can be built with latest gcc and run with latest qemu (gcc 11 and QEMU 6 by far, and should work on higher version).

## Setup

If you want to boot the Linux 0.11 from hard disk, you can download image file from [oldlinux.org](http://www.oldlinux.org/).

```bash
wget http://oldlinux.org/Linux.old/bochs/linux-0.11-devel-040923.zip
unzip -j linux-0.11-devel-040923.zip */hdc-0.11-new.img
mv hdc-0.11-new.img hdc-0.11.img
rm linux-0.11-devel-040923.zip
```

Install dependencies on Ubuntu:

```bash
sudo apt install build-essential gcc-multilib bin86 qemu-system-i386
```

## Boot the kernel

Build the kernel:

````bash
make -j
````

Boot the kernel with qemu:

```bash
make start
```

Or use specific QEMU options to boot the kernel:

```
qemu-system-i386 -m 16M -boot a -fda Image -hda hdc-0.11.img -display curses
```

## License

The Linux kernel is licensed under GPLv2.
