# automated-dual-boot-script
Single Block Self Division
Automated Dual-Boot Setup Script for Linux Mint (Single Drive)

Introduction

This script automates the installation of Linux Mint alongside a pre-existing Windows 11 installation on a single NVMe SSD. This approach eliminates the need for external bootable media (like USB drives) by leveraging GRUB 2 to boot the Linux Mint ISO directly from the Windows partition. This streamlines the dual-boot setup process and makes it easily repeatable.

Disclaimer

I am not affiliated with Microsoft, Linux Mint, GRUB 2, or any other software or hardware mentioned in this guide. I offer no warranty or guarantee for:

The accuracy of this guide.
The functionality of the provided script.
The safety of your system or data.
Prerequisites

A computer running Windows 11 with an NVMe SSD.
Administrative privileges on the Windows machine.
A downloaded Linux Mint ISO file (checksum verification highly recommended).
An optional backup of your important data (strongly recommended before making any system modifications).
Software Requirements

grub2win for GRUB 2 installation on Windows.
A Linux Live Boot environment (the Linux Mint ISO itself will provide this).
Script Overview

System Preparation:

Optional but highly recommended: Back up your important data.
Verify the downloaded Linux Mint ISO file using its checksum hash.
Shrink the Windows partition. This can be accomplished using either:
PowerShell commands within Windows (for script automation).
Disk partitioning tools available within the Linux Mint Live environment.
GRUB 2 Installation:

Disable Secure Boot in the BIOS settings (refer to your system's documentation).
Install grub2win on your Windows machine.
Use grub2win to create a new boot entry for the Linux Mint ISO file.
Configure the boot entry to point to the Linux kernel and initrd image within the ISO (typically located in /casper/boot/).
Linux Mint Installation:

Reboot your system.
Select the newly created GRUB 2 boot entry to launch the live Linux Mint environment.
Proceed with the graphical Linux Mint installation, allocating the freed space during partitioning.
Post-Installation:

The installer will handle GRUB 2 configuration for the dual-boot setup.
Reboot your system to verify the functional dual-boot environment.
