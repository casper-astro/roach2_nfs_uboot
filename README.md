roach2_nfs_uboot
================

This repository contains the files required to boot ROACH1/2 using NFS.

You will need to configure your tftp server to serve these boot files (kernel and uImage) to ROACH hosts. If using the combined TFTP/DHCP server `dnsmasq`, this means placing them in a directory refered to by `dnsmasq`'s `tftp-root` configuration parameter.

An example `dnsmasq` configuration file is provided, which hosts the boot files from the `/srv/tftpboot/` directory. This config file will allow `dnsmasq` to serve up either ROACH1 or ROACH2 files, based on the MAC address of a booting board.
In the provided example, the TFTP / DHCP server has the IP address `10.0.1.1`, and will serve IP addresses on the `10.0.1.xxx` subnet.

You will also need a root filesystem for your chosen board. You can obtain these in tar.gz form [here (ROACH2)](https://drive.google.com/file/d/1vdTiA1MazQ7_HBKMc3J9Hbpync2UWM7w/view?usp=sharing) or [here (ROACH1)](https://drive.google.com/file/d/1kQX7lvX7HQwaUMdYmhc7_dU2dh9aaloO/view?usp=sharing).

These filesystems should be extracted and referenced in your `dnsmasq` configuration file using the DHCP `root-path` option. See the provided exmaple for more details.
