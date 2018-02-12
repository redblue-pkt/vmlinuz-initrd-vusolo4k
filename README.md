# vmlinuz_initrd_vusolo4k
non official tweak version of initrd with multiboot support (11 partitions, 4 different firmware is possible)

We need:

#
# FOR MULTIBOOT
#

# new files
kernel_1_auto.bin
kernel_2_auto.bin
kernel_3_auto.bin
kernel_4_auto.bin
rootfs_1.ext4.tar.bz2
rootfs_2.ext4.tar.bz2
rootfs_3.ext4.tar.bz2
rootfs_4.ext4.tar.bz2
# standard files
initrd_auto.bin
rootfs.tar.bz2 <- dummy file
kernel_auto.bin <- dummy file
imageversion
# optional files
reboot.update
force.update

#
# FOR STANDARD UPGRADE or COMBACK FROM MULTIBOOT TO STANDARD BOOT
#

# standard files
initrd_auto.bin
rootfs.tar.bz2
kernel_auto.bin
imageversion
# optional files
force.update
reboot.update

And recompile kernel without line "root=/dev/mmcblk0p4 rootwait rw rootflags=data=journal debug" in your .config.
