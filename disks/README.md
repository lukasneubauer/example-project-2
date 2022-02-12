# Disks

The goal of this project is to provide useful information about storage devices, i.e.: HDD, SSD and USB.

## Scripts

* **disks**: lists overall information about each storage device attached to the system
* **disks-analyze-bad-blocks**: analyzes bad blocks on specific storage device
* **disks-analyze-speed**: analyzes read and write speed on specific storage device

### Script: disks

This script displays table of useful information about storage device.

Fields **Read speed** and **Write speed** display only **n/a**. To display real data, script **disks-analyze-speed** has to be run first.

Field **Bad blocks** displays only **n/a**. To display real data, script **disks-analyze-bad-blocks** has to be run first.

### Script: disks-analyze-bad-blocks

This script analyzes bad blocks of specific storage device. To run this script, all partitions on said storage device have to be unmounted.

### Script: disks-analyze-speed

This script analyzes read and write speed of specific storage device. To run this script, at least one partition on said storage device has to be mounted.
