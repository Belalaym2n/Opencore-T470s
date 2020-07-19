# Opencore-T470s

***It should go without saying but I will say it anyway. Hackintoshing is dangerous and could ruin your hardware permanently, I take no responsibility for your stuff, please Hackintosh at your own risk. I own nothing, everything belongs to Apple/Lenovo/OpenCore Team. Thanks.***

I'm creating this repository for those who might be trying to Hackintosh a computer that is similar to mine. I will continue to update the repository every few weeks/months as I improve my ACPI and Kext loadout. 

Currently running 10.5.6 Catalina on OC 0.5.9

### Hardware Config: 

1. Make and Model: Lenovo Thinkpad T470s
2. Processor and Chipset: Intel Core i5 6300u / Intel Skylake 100 series chipset
3. Graphics: Intel HD 520
4. Monitor: 1080p with Multi-touch 
5. Storage: HP ex920 NVMe 1 TB SSD
6. RAM: 12 GB DDR4
7. 1 x PS/2 Trackpad + Trackpoint 
8. 1 x PS/2 Keyboard
9. 1 x USB 3.0 card reader
10. 3 x USB 3.0 type a ports
11. 1 x TB3/USB C port
12. 1 x HDMI port
13. 1 x 3.5mm mic/headphone jack
14. 1 x smart card reader
15. 1 x WWAN network sim


### Currently functioning:

1. All basic functions including sleep/wake and boot without error 
2. Trackpoint and Trackpad with gesture support and Keypad buttons function as well
3. Touchscreen
4. Cardreader @ usb 3.0 speeds
5. USB type A ports
6. TB3 (Alpine Ridge)/USB type C works. However the ports have only been tested with standard USB 3.0 devices, since I do not posess and working TB3/USB3.1 devices


### Untested

1. BT/Wifi - My card is on order and I will update the system with appropriate Kexts once it is delivered. 
2. WWAN
3. Smart Card Reader


**Note on Keyboard Shortcuts**

Due to system instability being caused by SSDT-KBD.aml, I have removed the ssdt and replaced it with a couple of smaller SSDTS with more circumscribed functionality. Currently on Volume Controls and Brightness Controls are working as intended on the Laptop Keyboard. I am unlikely to bother further improving this. 


## Installation Instructions:

Please follow Dortania OC Vanilla guide to create ACPI, gather Kexts, and create installer. I would recommend reading through the entire process even if you are going to just copy paste this repo into your EFI folder; it will give you the ability to debug and upgrade your OC install in the future. 


**BIOS Settings**

1. Config 
   - USB UEFI Bios Support -> Enabled
   - Keyboard Mouse
     - Trackpoint -> Enabled
     - Trackpad -> Enabled
   - Display
     - Total Graphics Memory -> 512 MB
     - Boot Time Extension -> Disabled
   - Thunderbolt 2
     - Wake by TB3 -> Disabled
     - Support in Preboot Env -> Enabled
2. Security
   - Fingerprint 
     - Predesktop Auth -> Disabled
     - Security Mode -> Normal
   - Security Chip
     - TPM 2.0
     - Security Chip -> Disabled/All
   - Memory Protection -> Enabled
   - Virtualization
     - Intel Virtualization -> Enabled
     - Intel VT -d -> Disabled
   - I/O port access -> Enable All
   - Secure Boot -> Disabled
   - Intel SGX -> Disabled
   - Device Guard -> Disabled   
3. Startup
   - UEFI/Legacy -> Legacy only
   - CSM Support -> No
