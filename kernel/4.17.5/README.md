You may download the compiled 4.17.5 PPC64 book3e kernel and related modules from my Google Drive here


https://drive.google.com/file/d/1w4x0OPgSs-ZkqqJLPRiCrDNfVhEn_Nb8



make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- oldconfig
make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- menuconfig
make -j2 ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- uImage
make -j2 ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- modules
make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- modules_install INSTALL_MOD_PATH=/home/mario/Documents/kernel_output/kernel_4.17.5/modules/

make ARCH=powerpc SUBARCH=ppc64 CROSS_COMPILE=powerpc64-linux-gnu- clean

sudo apt install device-tree-compiler
dtc -O dtb -o /home/mario/Documents/kernel_output/kernel_4.17.5/t2080rdb.dtb /home/mario/Documents/kernels/linux-4.17.5/arch/powerpc/boot/dts/fsl/t2080rdb.dts