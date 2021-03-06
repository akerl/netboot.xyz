# netboot.xyz 
[![Build Status](https://travis-ci.org/antonym/netboot.xyz.svg?branch=master)](https://travis-ci.org/antonym/netboot.xyz) [![Gitter](https://badges.gitter.im/antonym/netboot.xyz.svg)](https://gitter.im/antonym/netboot.xyz?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

![netboot.xyz menu](img/netboot.xyz.gif)

### Bootloader Downloads

These iPXE disks will automatically load into [boot.netboot.xyz](https://boot.netboot.xyz):

| Type | Bootloader | Description |
|------|------------|-------------|
|ISO| [netboot.xyz.iso](https://boot.netboot.xyz/ipxe/netboot.xyz.iso)| Used for CD/DVD, Virtual CDs like DRAC/iLO, VMware, Virtual Box|
|USB| [netboot.xyz.usb](https://boot.netboot.xyz/ipxe/netboot.xyz.usb)| Used for creation of USB Keys|
|Kernel| [netboot.xyz.lkrn](https://boot.netboot.xyz/ipxe/netboot.xyz.lkrn)| Used for booting from GRUB/EXTLINUX|
|DHCP| [netboot.xyz.kpxe](https://boot.netboot.xyz/ipxe/netboot.xyz.kpxe)| DHCP boot image file, uses built-in iPXE NIC drivers|
|DHCP-undionly | [netboot.xyz-undionly.kpxe](https://boot.netboot.xyz/ipxe/netboot.xyz-undionly.kpxe)| DHCP boot image file, use if you have NIC issues|

SHA256 checksums are generated during each build of iPXE and are located [here](https://boot.netboot.xyz/ipxe/netboot.xyz-sha256-checksums.txt).  You can also view the scripts that are embedded into the images [here](https://github.com/antonym/netboot.xyz/tree/master/ipxe/disks).

### What is netboot.xyz?

[netboot.xyz](http://netboot.xyz) is a way to select various operating system installers or utilities from one place within the BIOS without the need of having to go retrieve the media to run the tool.  [iPXE](http://ipxe.org/) is used to provide a user friendly menu from within the BIOS that lets you easily choose the operating system you want along with any specific types of versions or bootable flags.

You can remote attach the ISO to servers, set it up as a rescue option in Grub, or even set up your home network to boot to it by default so that it's always available.

### Getting started

Download the bootloader of your choice from the links above and add it to your favorite virtualization tool to start testing out netboot.xyz.  These are precompiled versions of the latest version of [iPXE](https://github.com/ipxe/ipxe) that will chainload you to [https://boot.netboot.xyz](https://boot.netboot.xyz).  If you have DHCP it'll automatically attempt to boot from DHCP.  If you need to set a static IP address, hit the 'm' key during boot up for the failsafe menu and choose manual network configuration.

If you already have iPXE up and running on the network, you can hit netboot.xyz at anytime by typing:

    chain --autofree https://boot.netboot.xyz

You'll need to make sure to have [DOWNLOAD_PROTO_HTTPS](https://github.com/ipxe/ipxe/blob/master/src/config/general.h#L56) enabled when compiling iPXE.

### Operating Systems

#### What Operating Systems are currently available on netboot.xyz?

* [Antergos](https://antergos.com)
* [Arch Linux](https://www.archlinux.org)
* [Architect Linux](http://sourceforge.net/projects/architect-linux)
* [BlackArch Linux](https://blackarch.org)
* [CentOS](https://centos.org)
* [CoreOS](https://coreos.com/)
* [Debian](https://debian.org)
* [Fedora](https://fedoraproject.org)
* [FreeBSD](https://freebsd.org)
* [Gentoo](https://gentoo.org)
* [Kali Linux](https://www.kali.org)
* [Mageia](http://www.mageia.org)
* [Manjaro Linux](https://manjaro.github.io)
* [Microsoft Windows](https://www.microsoft.com)
* [MirOS](https://www.mirbsd.org)
* [OpenBSD](http://openbsd.org)
* [OpenSUSE](http://opensuse.org)
* [RancherOS](http://rancher.com/rancher-os/)
* [Scientific](http://scientificlinux.org)
* [Tiny Core Linux](http://tinycorelinux.net)
* [Ubuntu](http://www.ubuntu.com/)

#### Hypervisors

* [Citrix XenServer](http://xenserver.org)

#### Utilities

* [AVG Rescue CD](http://www.avg.com/us-en/avg-rescue-cd)
* [Clonezilla](http://www.clonezilla.org/)
* [DBAN](http://www.dban.org/)
* [GParted](http://gparted.org)
* [Grml](http://grml.org)
* [HDT](http://www.hdt-project.org/)
* [Memtest](http://www.memtest.org/)
* [Partition Wizard](http://www.partitionwizard.com)
* [Pogostick - Offline Windows Password and Registry Editor](http://pogostick.net/~pnh/ntpasswd)
* [Super Grub2 Disk](http://www.supergrubdisk.org)
* [SystemRescueCD](https://www.system-rescue-cd.org)
* [Ultimate Boot CD](http://www.ultimatebootcd.com)

### Source Code

The source code for netboot.xyz is located [here](https://github.com/antonym/netboot.xyz).

### Contributing

New version of an operating system out?  Found one that network boots well with iPXE?  Pull requests are welcomed and encouraged and helps me out a ton!  Feel free to issue a pull request for new versions or tools that you might find useful.  Once merged into master, [Travis CI](https://travis-ci.org/antonym/netboot.xyz) will regenerate new versions of [iPXE from upstream](https://github.com/ipxe/ipxe) and deploy the latest changes to netboot.xyz.

### Testing New Branches

Under the Utilities menu on netboot.xyz, there's an option for ["Test netboot.xyz branch"](https://github.com/antonym/netboot.xyz/blob/master/src/utils.ipxe#L61).  If you've forked the code and have developed a new feature branch, you can use this option to chainload into that branch to test and validate the code.  All you need to do is specify your github user name and the name of your branch or abbreviated hash of the commit.

### Feedback

Feel free to open up an [issue](https://github.com/antonym/netboot.xyz/issues) on Github, swing by [Freenode IRC](http://freenode.net/) in the [#netbootxyz](http://webchat.freenode.net/?channels=#netbootxyz) channel, or ping us on [Gitter](https://gitter.im/antonym/netboot.xyz?utm_source=share-link&utm_medium=link&utm_campaign=share-link).  Follow us on [Twitter](https://twitter.com/netbootxyz) or like us on [Facebook](https://www.facebook.com/netboot.xyz)!
