
## booting sequence

1-Poost --> power on self test --> test the minimum hardware to boot 
2-BIOS --> find all the bootable devices and compare its setting
(may boot from disk , sdcard , flash , network , ........)
3-load initial program loader(IPL) small code exist in the mother board 
try to execute the boot loader 
4-start boot loader (GRUB) exist in MBR
512 byte MBR 
64b --> partition table
446b --> boot loader
2b --> for magic number (checksum)
446 first stage boot loader that load the second stage boot loader exist in /boot ---> big size 
5-boot loader load the kernel 
6-kernel start init system (kernel + initramfs)
- load some drivers by initramfs
- mount file system read only
- if there is a problem in the file system , it will fail to continue 
- if everything is ok remount the file system as read write 
- start init 
7-systemd start all the services
