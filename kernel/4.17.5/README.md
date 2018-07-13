You may download the compiled 4.17.5 PPC64 book3e kernel and related modules from my Google Drive here


https://drive.google.com/file/d/14ikR98MEMBFpLDCE86Gf6tuC8MB2-45S/view?usp=sharing


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


You may want to compile the dtb file (a flattened device-tree block with header in one binary blob) for the T2080rdb using the dts file (a text file containing a "source" for a device-tree) coming with the kernel you should install the device tree compiler by entering

`sudo apt install device-tree-compiler`

To compile a dtb file from the T2080rdb dts file

`dtc -O dtb -o /myCustomPath/t2080rdb.dtb /kernel/arch/powerpc/boot/dts/fsl/t2080rdb.dts`

Please note that you MUST customize the default t2080rdb.dts (and related dtsi) files to enable video card support on the T2080rdb devkit.



