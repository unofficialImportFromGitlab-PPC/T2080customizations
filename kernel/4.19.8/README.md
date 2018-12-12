You may download the already compiled 4.19.8 kernel for PPC64 book3e e6500 and related modules from my Google Drive here


https://drive.google.com/file/d/1ZWOuETT16Tq8GaMsTcv66OgVIcc3UbD7/view?usp=sharing


To cross-compile a kernel using the provided .config file follow this procedure (tested on Ubuntu 18.04 amd64).

1) be sure to install all packages required for compiling a kernel and to cross-compile a ppc64 kernel

2) install the required packages for generating a U-Boot kernel image ("sudo apt install u-boot-tools")

3) download a tarball (.tzr.gz) kernel file from https://www.kernel.org/

4) extract the kernel in a folder

5) copy the provided ".config" file inside the kernel folder

6) load the configuration file and check if it against your kernel

`make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- oldconfig`

7) you may check the kernel configuration using the kernel buil-in gui

`make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- menuconfig`

8) cross-compile the kernel entering

`make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- uImage`

9) cross-compile the required kernel modules entering

`make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- modules`

10) grab the generated kernel image for U-Boot, you will find it in "arch/powerpc/boot/uImage"

11) grab the kernel modules placing them in a custom folder entering

`make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- modules_install INSTALL_MOD_PATH=/myCustomPath/kernel/modules/`


If you alreadey cross-compiled a kernel and then you want to cross-compile another one (for example after changing the configuration file), you should clean your building environment entering

`make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- clean`


In order to correctly initialize your T2080rdb board, your U-Boot requires a Device Tree Blob (dtb) file and the Freescale/NXP DPAA FMAN microcode.


You may obtain the dtb file ("uImage.dtb") from here

https://gitlab.com/oshw-powerpc-notebook/T2080customizations/blob/master/device_tree/

You may obtain the DPAA FMAN microcode from here

https://gitlab.com/oshw-powerpc-notebook/T2080customizations/tree/master/fman_microcode


Infos on Device Tree Blobs (dtb)

http://www.informit.com/articles/article.aspx?p=1647051&seqNum=5


Infos on Freescale/NXP DPAA

http://cache.freescale.com/files/training/doc/ftf/2014/FTF-NET-F0146.pdf

http://cache.freescale.com/files/training/doc/ftf/2014/FTF-NET-F0111.pdf



