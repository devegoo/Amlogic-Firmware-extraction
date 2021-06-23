# Amlogic-Firmware-extraction FOR LINUX

code is not working in 100% but extract function working

"You’ll just need aml_sdc_burn.ini and aml_sdc_burn.UBOOT, plus the IMG file itself to create a bootable mass storage device.

Find the device for your micro SD card (formatted with FAT32) with lsblk"


sudo umount /dev/sdX*

sudo dd if=aml_sdc_burn.UBOOT of=/dev/sdX bs=1 count=442

sudo dd if=aml_sdc_burn.UBOOT of=/dev/sdX seek=1 skip=1 bs=512

sync


"and finally, re-mount the SD card/flash drive, 

Copy the firmware file and aml_sdc_burn.ini to the root of the device,

and rename the firmware to aml_upgrade_package.img to match the string in aml_sdc_burn.ini"


cp aml_sdc_burn.ini aml_sdc_burn.UBOOT [device-mount-point] 

cp <your_aml_firmware_file_name>.img [device-mount-point]/aml_upgrade_package.img 

sudo umount /dev/sdX*



"Now make sure no other USB devices or SD cards are inserted in the TV box,

and insert your bootable (micro) SD card or USB flash drive into the TV box. If your TV box is fully bricked, you have nothing to do,

and the update should start straight away, but if it is partially bricked or just working fine,

you still need to press the recovery button, apply power, and release the button in order to enter recovery mode. The upgrade should then start automatically"
