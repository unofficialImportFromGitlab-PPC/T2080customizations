The .dtb file, a flattened device-tree block with header in a binary blob loaded by U-Boot at boot time.
The .dtb is obtained by compiling a .dts file, a text file containing a "source" for a device-tree that may include reference to other .dtsi files, which are additional sources.
To compile a .dtb from a .dts you need a "device tree compiler", that is installed entering

`sudo apt install device-tree-compiler`

To start the compilation download all .dts and dtsi files in this folder and enter

`dtc -O dtb -o ./uImage.dtb ./t2080rdb.dts`

Please note that this the file "t2080si-post.dtsi" has been modified in order to accomodate a video card attached on the onboard PCIe 4x (J20) using a PCIe 4x to PCIe 16x adaptor cable.
Another file altered to accomodate a PCIe video card is the file "t208xrdb.dtsi".