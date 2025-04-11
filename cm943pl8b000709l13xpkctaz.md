---
title: "exFAT, the 64-bit upgrade to FAT32"
seoTitle: "exFAT: The 64-bit upgrade to FAT32"
seoDescription: "Learn how to format drives to exFAT on Linux, supporting large files across operating systems, with this clear, step-by-step guide"
datePublished: Sat Apr 05 2025 10:59:08 GMT+0000 (Coordinated Universal Time)
cuid: cm943pl8b000709l13xpkctaz
slug: exfat-the-64-bit-upgrade-to-fat32
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/1qL31aacAPA/upload/405833446db1c1be2be883220b7b3e92.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1743850687503/e1ddf6ed-467b-4e01-8f07-04a94579b86a.png
tags: linux, file-system, fat32, exfat

---

Most drives you buy are preformatted with a FAT32 file system by the manufacturer. This file system is interoperable with all operating systems. However, it is archaic in the sense that it was designed for use on 32-bit systems and can only handle a maximum file size of **~4 GB** (**precisely 2<sup>32</sup> − 1 bytes**).  
  
The exFAT file system is an upgrade to FAT32 designed for use on 64-bit systems and is interoperable with most modern operating systems. This is why it can handle file sizes greater than 4 GB. This article shows how you should format a USB or external hard drive to the exFAT file system on Linux Mint or Ubuntu.

<div data-node-type="callout">
<div data-node-type="callout-emoji">🔴</div>
<div data-node-type="callout-text">Back up the data on your drive. Formatting a drive will destroy all the data in a drive.</div>
</div>

## **Identify the USB Drive**

Use the `fdisk` command to list all connected drives and identify your USB drive. `fdisk`, short for **format disk**, is a powerful CLI utility used to manage the structure of a drive. It can create, delete, and resize partitions.

```bash
sudo fdisk -l
```

The `-l` flag lists the partition tables for specified disks or all disks if no disk is specified. It lets you view details about all the available partitions in your system and see their `/dev` names. For example `/dev/sda` or `/dev/sdb`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1743847467660/744a8da0-d7d0-4ad4-ba5b-226ed434ec0d.png align="center")

## Unmount the Drive

Make sure the drive is not mounted to ensure that the operation is performed safely, and correctly and to prevent data corruption.

Use the `umount` command. It is a CLI utility used to manually unmount filesystems on Linux and other Unix-like operating systems.

```bash
sudo umount /dev/sdb1
```

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">Replace <code>/dev/sdb1</code> with the actual partition name of your USB drive.</div>
</div>

## **Install exFAT Utilities**

exFAT utilities are programs which will help format drives to ExFAT, FAT, FAT32, or NTFS file systems completely. Run the following commands to install them:

```bash
sudo apt install exfat-utils
```

or

```bash
sudo apt install exfatprogs
```

## Format the Drive

The `gdisk` CLI utility is a text-mode menu-driven program for the creation and manipulation of partition tables. It is similar to `fdisk`, but **gdisk** modifies GPT partitions. It also has the capability of transforming MBR partitions or BSD disklabels into GPT partitions.

```bash
sudo gdisk /dev/sdb1
```

When `gdisk` starts, it performs a scan for four types of existing partition tables and displays the results:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1743849698994/7d0af5bd-1aa4-4b21-934e-211c23399a1d.png align="center")

MBR is the common Master Boot Record partitioning system. There are four MBR states: MBR only, protective, hybrid, or not present.

BSD is the Berkeley Standard Distribution (BSD) disk label system used on some computers that run BSD Unix, like FreeBSD, OpenBSD, i.a.  
APM is the Apple Partition Map used on the `680x0` and PowerPC-based Macintoshes. The BSD and APM scans report either present or not present.

GPT is the GUID Partition Table. GPT can report three states: present, not present, or damaged.

## Create a new GPT partition table

The defaults will create a new partition that spans the whole drive. Be sure to choose the correct type `0700`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1743850433320/c4a4119b-1fff-457a-9aff-262b1b3b8114.png align="center")

```bash
sudo mkfs.exfat /dev/sdb1
```

The drive is now be readable and writable on Linux, OSX, and Windows.

##