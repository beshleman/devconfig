# devconfig
A repo containing the configurations I use during development (u-boot, kernel, toolchain)

beaglebone/
	For kernel development on the BeagleBone Black:

beaglebone/beaglebone_defconfig
	defconfig for compiling the linux kernel, tested on 4.19
	upstream: https://github.com/beagleboard/linux.git

beaglebone/host/
	Config files for the host machine

	dhcpcd.conf - DHCP configuration (server)
		Goes to /etc/dhcpcd.conf

	exports - NFS server (not really used in my setup), for /etc/exports

	tftpd -  TFTP server config, found in /etc/conf.d/tftpd, for transferring files (zImage and dtb)

beaglebone/target/
	Files for target (the beaglebone itself)

	interfaces - describes addressing for eth0 and usb0, only usb0 is used (ethernet-over-usb)
		goes in /etc/network/interfaces

	uboot.txt - Uboot config info
		This isn't a config file (though it could be turned into a uEnv.txt)
		It is just shows a session that displays that parameters
		Notably is the tftp transfers, bootz, mmc writing and loading, and bootargs
