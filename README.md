# bootable-USB
How to Create a Bootable USB from ISO on Linux
This guide shows how, with minimal effort, to create a bootable USB from ISO in Linux using the built-in dd comm.

1. Connect the USB device and find the name under which it is presented on your computer. You can do this easily using the lsblk command.

As you can see, it is mounted as “sdb” in our case and can thus be accessed with its full path as “/dev/sdb.” However, if you have multiple USB sticks already connected to your system, the drive you’d like to target might be “/dev/sdc,” “/dev/sdd,” etc.

2. Unmount and Format the USB Device
After confirming your target drive, you need to unmount it before formatting it.

sudo umount /dev/sdb*
