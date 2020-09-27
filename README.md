# hackintosh
A repo to keep OS X related hacks. EFI for NUC10i7 and others.

# EFI
This folder contains the Apple OS X Catalina EFI which works for me on the NUCi7FNH2. SD Card reader doesn't work but I use an Akasa Turing FX fanless case which removes the SD Card slot.  
Bluetooth, LAN, USB ports are functional.  
Wifi is functional too - but you wish it wasn't. It appears as a secondary LAN, the EFI from this Git repo has to be modified with the SSID and password fo your WIFI. The speed i got is 20/20 Mbit/s vs. the ˜650/800 Mboit/s down/upload speed of Windows 10 with Intel Wifi 6 drivers, the NUC being in the same spot physically.  
The EFI should work with the latest Catalina version 10.15.7.

# Usage

Clone the repo and modify EFI/OC/Kexts/itlwmx.kext/Content/Info.plist, change YOURSSID and YOURPASSWORD values.
Download Catalina and Create an USB drive with UniBeast. When the drive is created, the EFI partition remains mounted and not hidden - do not eject USB drive yet.
After UniBeast finished creating the drive, delete the content of the EFI folder from the EFI partition of the USB drive, and copy the content of the EFI folder from this repo (with your SSID and password).
Eject USB drive to make sure content is synced (or run `sync`in the terminal).  

Disable Secure Boot and Legacy Boot in the BIOS of the NUC, make sure BT and WIFI are enabled.

Boot USB and install Catalina to NUC. If it's a new drive you're isntalling to, need to use first the Disk Utility from the installation tools to create an AFPS volume.
