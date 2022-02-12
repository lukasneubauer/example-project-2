# Grub

The goal of this project is to provide useful utility scripts for the Grub bootloader.

## Scripts

Below is a description of each script in this project.

### Script: install-on-live-os

This script is intended to run in live environment (Live CD), because the bootloader needs to be installed on system partition, which has to be unmounted, but this cannot be done when booted into the bare metal system.

### Script: restore-on-main-os

This script is intended to run on bare metal system, and it only updates the bootloader configuration.
