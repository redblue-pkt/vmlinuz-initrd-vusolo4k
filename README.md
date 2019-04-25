
# vmlinuz_initrd_vusolo4k
non official tweak version of initrd with multiboot support (11 partitions, 4 different firmware is possible)

We need:

FOR MULTIBOOT

- new files
  - kernel_1_auto.bin
  - kernel_2_auto.bin
  - kernel_3_auto.bin
  - kernel_4_auto.bin
  - rootfs_1.ext4.tar.bz2
  - rootfs_2.ext4.tar.bz2
  - rootfs_3.ext4.tar.bz2
  - rootfs_4.ext4.tar.bz2
  
- standard files
  - initrd_auto.bin
  - rootfs.tar.bz2 <- dummy file
  - kernel_auto.bin <- dummy file
  - imageversion
  
- optional files
  - reboot.update
  - force.update

FOR STANDARD UPGRADE or COMBACK FROM MULTIBOOT TO STANDARD BOOT

- standard files
  - initrd_auto.bin
  - rootfs.tar.bz2
  - kernel_auto.bin
  - imageversion
  
- optional files
  - force.update
  - reboot.update

And recompile kernel:

    #
    # Boot options
    #
    CONFIG_USE_OF=y
    CONFIG_ATAGS=y
    # CONFIG_DEPRECATED_PARAM_STRUCT is not set
    CONFIG_ZBOOT_ROM_TEXT=0
    CONFIG_ZBOOT_ROM_BSS=0
    CONFIG_ARM_APPENDED_DTB=y
    CONFIG_ARM_ATAG_DTB_COMPAT=y
    # CONFIG_ARM_ATAG_DTB_COMPAT_CMDLINE_FROM_BOOTLOADER is not set
    CONFIG_ARM_ATAG_DTB_COMPAT_CMDLINE_EXTEND=y
    CONFIG_CMDLINE="NULL"
    CONFIG_CMDLINE_FROM_BOOTLOADER=y
    # CONFIG_CMDLINE_EXTEND is not set
    # CONFIG_CMDLINE_FORCE is not set
    CONFIG_KEXEC=y
    CONFIG_ATAGS_PROC=y
    # CONFIG_CRASH_DUMP is not set
    CONFIG_AUTO_ZRELADDR=y

