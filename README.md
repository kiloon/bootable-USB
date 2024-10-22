# bootable-USB
How to Create a Bootable USB from ISO on Linux
This guide shows how, with minimal effort, to create a bootable USB from ISO in Linux using the built-in dd comm.

1. Connect the USB device and find the name under which it is presented on your computer. You can do this easily using the lsblk command.

As you can see, it is mounted as “sdb” in our case and can thus be accessed with its full path as “/dev/sdb.” However, if you have multiple USB sticks already connected to your system, the drive you’d like to target might be “/dev/sdc,” “/dev/sdd,” etc.

2. Unmount and Format the USB Device
After confirming your target drive, you need to unmount it before formatting it.

sudo umount /dev/sdb*

Next, we need to format the unmounted drive. Let’s do this with the following command:

sudo mkfs.vfat -I /dev/sdb

3. Create a Bootable USB Using the dd Command

   We’re ready to copy the ISO file to the USB drive using the dd command. I’d recommend navigating to the directory where you downloaded the ISO. Let’s say you put it in your user’s “Downloads” directory.

cd ~/Downloads

Since we’re already in the right directory, we can use the following command to write ISO to USB and create a bootable USB stick:

sudo dd bs=4M if=filename.iso of=/dev/sdb status=progress

Where “filename.iso” is, of course, replaced by the actual name of your ISO file.

bs: Sets the default block size.
if: Stands for “input file.” It is used to specify the location of the ISO file.
of: Stands for “output file.” It sets where to write the ISO file. In our case, it is “/dev/sdb.”

That’s all. You can use the USB drive as Linux installation media or a software installer when the process is finished. You can also use the same method to turn an installation ISO image file into a bootable USB stick.
