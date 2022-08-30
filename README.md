OpenCore bootloader configured for z690 plus tuf wifi d4 - i7 12700 - rx 6800 hackintosh

READ THE READ ME FILE IN THE .ZIP ARCHIVE

Before using this EFI, you'll need to make some adjustments.
Update your BIOS first!!!!!! Your bios shall have:
•	Enabled Virtualization and VT-d
•	Disabled iGPU Multi monitor and primary display set to PCIE
•	Above 4g Decoding enabled and BAR Resize on AUTO
•	Enabled XHCI Handoff
•	Disabled CSM
•	Disabled Network Stack
•	Disabled Fastboot and Secure Boot
•	Suggested: enabled XMP

1.	Generete a MacPro7,1 SMBIOS using macserial, a tool you can find in OpenCorePKG under the Utilities folder. However, for a easier use with a more comfortable GUI, I suggest you to use Corpnewt’s GenSMBIOS tool.
BOTH TOOLS NEED PYTHON INSTALLED.
2.	Using Propertree, put your en0 LAN module (you can easily check that with Hackintool) MAC Address in PlatformInfo>Generic>ROM in your config.plist. Just make sure to remove every “:” between every couple of symbols. (i.e.: 36:E3:56:EE:23 becomes 36E356EE23).
3.	UNLOCK YOUR CFG-Lock ON YOUR MOTHERBOARD’S FIRMWARE. YOU MUST DO THIS
4.	Your AppleALC layout (alcid=11) is loaded via the alcid boot-arg. You can put under DeviceProperties in your config.plist following this guide. Just remember to delete it from NVRAM>ADD> 7C436110-AB2A-4BBB-A880-FE41995C9F82>boot-args.

Credits:
@maydayalaska (Telegram|Reddit) for creating the EFI
Utopia Team for the debug EFI
Corpnewt for the tools
Dortania for the guides
Acidanthera for OpenCore
