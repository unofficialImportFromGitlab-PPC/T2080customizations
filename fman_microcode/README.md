These are the microcode families of the Frame Manager hardware block in QorIQ
products. Specific platforms require specific binaries, and those also have to
further match specific software versions (Frame Manager Driver -- FMD).

Latest Releases available:

IPACC IRAM Package Alpha Release 106_x_18 
DSAR IRAM Package Alpha Release 107_x_2
IPACC + Next Generation CAPWAP  108_x_9

Versioning numbers significance:

First number:
	Primary Major number: Encodes the major features supported by this release
	106: IPACC
	107: DSAR + partial IPACC
	108: NG CAPWAP + FE + IPACC

_106_
This IRAM package includes the following main features:
Custom Classification (CC), Independent-Mode (IM),
Host-Commands (HC), IPv4/6 Fragmentation (IPF),
IPv4/6 Reassembly (IPR), IPsec and Header Manipulation (HM).
Release Notes: DPAA_IPACC_ReleaseNote.pdf

_107_
This IRAM package includes the following main features: 
Custom Classification (CC), Independent-Mode (IM), 
Host-Commands (HC) and Deep Sleep Auto Response (DSAR). 
For DSAR the following features are supported: ARP, ICMP, ND and SNMP.
Release Notes: DPAA_DSAR_ReleaseNote.pdf

_108_
This IRAM package includes the following main features:
NG CAPWAP, Custom Classification (CC), Independent-Mode (IM), 
Host-Commands (HC), IPv4/6 Fragmentation (IPF),
IPv4/6 Reassembly (IPR), IPsec and Header Manipulation (HM).
Relese Notes: DPAA_NG_CAPWAP_ReleaseNote.pdf


    CC IM HC IPF IPR HM DSAR CAPWAP
106 +  +  +  +   +   +  -    -
107 +  +  +  -   -   -  +    -
108 +  +  +  +   +   +  -    +


Second number: 
	Secondary Major number: Encodes different HW revisions and specific minor features
	106.1:  FMANv2 without Software DMA Semaphore
	106.2:  FMANv2 with Software DMA Semaphore
	106.3:  FMANv3 Rev.1
	106.4:  FMANv3 > Rev.1

	107.4:  DSAR 

	108.4:  Full NG CAPWAP (with GRE additions)
	108.5:  Reduced NG CAPWAP (only for NG CAPWAP demo, without IM)

				
Third number: 
	Minor number: incremented when new minor enhancements or significant fixes are introduced


List of platforms and their appropriate latest ucode version:
<pre>
b4860_r2.2	fsl_fman_ucode_b4860_r2.2_106_4_18.bin (*)
		fsl_fman_ucode_b4860_r2.2_108_4_9.bin
ls1043_r1.1	fsl_fman_ucode_ls1043_r1.1_106_4_18.bin (*)
		fsl_fman_ucode_ls1043_r1.1_108_4_9.bin
ls1046_r1.0	fsl_fman_ucode_ls1046_r1.0_106_4_18.bin (*)
		fsl_fman_ucode_ls1046_r1.0_108_4_9.bin
p1023_r1.1	fsl_fman_ucode_p1023_r1.1_160_0_18.bin
p2041_r2.0	fsl_fman_ucode_p2041_r2.0_106_1_18.bin
p3041_r2.0	fsl_fman_ucode_p3041_r2.0_106_1_18.bin
p4080_r3.0	fsl_fman_ucode_p4080_r3.0_106_2_18.bin
p5020_r2.0	fsl_fman_ucode_p5020_r2.0_106_1_18.bin
p5040_r2.1	fsl_fman_ucode_p5040_r2.1_106_1_18.bin
t1024_r1.0	fsl_fman_ucode_t1024_r1.0_106_4_18.bin (*)
		fsl_fman_ucode_t1024_r1.0_107_4_2.bin
		fsl_fman_ucode_t1024_r1.0_108_4_9.bin
t1040_r1.1	fsl_fman_ucode_t1040_r1.1_106_4_18.bin (*)
		fsl_fman_ucode_t1040_r1.1_107_4_2.bin
t2080_r1.1	fsl_fman_ucode_t2080_r1.1_106_4_18.bin (*)
		fsl_fman_ucode_t2080_r1.1_108_4_9.bin
t4240_r2.0	fsl_fman_ucode_t4240_r2.0_106_4_18.bin (*)
		fsl_fman_ucode_t4240_r2.0_108_4_9.bin
</pre>
(*) denotes which is the default version