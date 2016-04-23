# MirrorVM Builder


## Overview

MirrorVM Builder will create a VirtualBox virtual machine
suitable for mirroring software repositories. The expected
scenario is to place the virtual machine image and its data
volume on an external hard drive for portability.


## Requirements

* [VirtualBox] 5.0, although should work with earlier
  versions.
* [Vagrant] 1.8

[VirtualBox]: https://www.virtualbox.org/
[Vagrant]: https://www.vagrantup.com/


## Hard Drive Preparation

The expected scenario is to use an external hard drive to
hold the virtual machine image and its data volume. The hard
drive should be partitioned as [GPT]:

|   # | Format                                          | Size         | Purpose               |
| ---:| ----------------------------------------------- | ------------ | --------------------- |
|   1 | [exFAT]                                         | about 100 GB | virtual machine files |
|   2 | any native Linux file system<br>e.g., ext4, xfs | remainder    | data volume           |

[GPT]: https://en.wikipedia.org/wiki/GUID_Partition_Table
[exFAT]: https://en.wikipedia.org/wiki/ExFAT


## Installation

TODO


## Creation Notes

Create boilerplate `Vagrantfile`

```Shell
vagrant init centos/7
```

Spinup virtual machine

```Shell
vagrant up --provider virtualbox
```