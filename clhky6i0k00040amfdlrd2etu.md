---
title: "Kali Linux on Android Devices"
seoTitle: "Set up Termux | Kali Linux on Android"
seoDescription: "Set up Termux by installing Kali Linux on an Android device"
datePublished: Thu Apr 07 2022 21:00:00 GMT+0000 (Coordinated Universal Time)
cuid: clhky6i0k00040amfdlrd2etu
slug: kali-linux-on-android-devices
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694185219325/1018ad10-795e-4b83-942c-15d6d48ed724.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694185495538/15b219a9-9af2-4f1a-afe3-4068cc9c2844.png
tags: linux, android, kali-linux, linux-for-beginners, nethunter

---

## Introduction

With Kali Linux installed on your smartphone, its utility becomes supercharged. This guide will help you set up the Kali Linux CLI on any Android device.

### pros

* I use it for programming on good old Vim when not around my PC but even that's barely scratching the tip of the iceberg.
    
* With Kali, you have a dynamic tool for penetrating networks, testing vulnerabilities, and safeguarding against potential threats.
    

Whether you're an IT professional, curious about Kali OS, an ethical hacker, or simply concerned about personal data security, this integration empowers you with tools and knowledge to stay up to date in today's digital landscape.

## Download Termux

First and foremost, you will download [Termux](https://termux.dev/en/).

Termux is a terminal emulator that works directly on Android devices **that have not been jailbroken/rooted**.

To download the app, you will either use the [F-Droid store](https://f-droid.org/en/packages/com.termux/) or the [official GitHub repository](https://github.com/termux/termux-app#github).

Downloading Termux via the Google Play Store is discouraged. This is because the [Termux version found on the Google Play Store is deprecated](https://github.com/termux/termux-app#google-play-store-deprecated), and thus it's bound to have dependency issues of one form or another.

## **Set-up Termux**

You'll update and upgrade your system using the following command:

```bash
apt update && apt upgrade -y
```

You also need to permit Termux to access your device's storage. To do this, run:

```bash
termux-setup-storage
```

## Set up Kali Linux

This is the final part of this guide.

To accomplish your goal, you will be setting up the Kali NetHunter Rootless Edition.

Kali NetHunter is a custom OS for Android devices. The Rootless Edition is for devices that have not been jailbroken/rooted.

Since Kali NetHunter is an open-source project, you don't need to worry about copyright infringement when utilizing it.

The system requirements will vary but, on the low end, you can set it up as a basic Secure Shell (SSH) server with no desktop, using as little as 128 MB of RAM (512 MB recommended) and 2 GB of disk space.

To begin with, you'll have to install `wget`. It is a computer program that retrieves content from web servers. To install it, we'll use the Termux package manager (`pkg`):

```bash
pkg install wget
```

After `wget` is installed, you'll fetch the NetHunter installation file:

```bash
wget -O install-nethunter-termux https://offs.ec/2MceZWr
```

Once the file is downloaded, you'll change its mode to make it executable so that you can install NetHunter by running it:

```bash
chmod +x install-nethunter-termux
```

Run the executable:

```bash
./install-nethunter-termux
```

## Using Kali Linux on Android

To start the Kali NetHunter command line interface, run:

```bash
nh
```

It is recommended to update Kali first thing after installation by running:

```bash
sudo apt update && sudo apt full-upgrade -y
```

The default root password is: `kali`.

To exit the Kali CLI or Termux CLI, run:

```bash
exit
```

Perform regular backups of your rootfs by stopping all NetHunter sessions and typing the following in a Termux session:

```bash
tar -cJf kali-arm64.tar.xz kali-arm64 && mv kali-arm64.tar.xz storage/downloads
```

That will put the backup in your Android download folder.  
*Note: on older devices, change “arm64” to “armhf”.*

## References

1. [The Termux website](https://termux.dev/en/).
    
2. [F-Droid store](https://f-droid.org/en/packages/com.termux/).
    
3. [Official GitHub repository](https://github.com/termux/termux-app).
    
4. [The Google Play Store version is deprecated](https://github.com/termux/termux-app#google-play-store-deprecated).
    
5. [What is Kali NetHunter?](https://www.simplilearn.com/tutorials/cyber-security-tutorial/what-is-kali-nethunter#:~:text=Kali%20Linux%20NetHunter%20is%20the,copyright%20infringements%20or%20other%20threats.)
    
6. [Kali NetHunter History](https://www.kali.org/docs/introduction/kali-nethunter-history/#:~:text=Kali%20NetHunter%20is%20a%20custom,desktop%20and%20makes%20it%20mobile.).
    
7. [Kali NetHunter System Requirements.](https://www.kali.org/docs/installation/hard-disk-install/#system-requirements)
    
8. [Kali NetHunter documentation](https://www.kali.org/docs/nethunter/nethunter-rootless/).
    
9. [Kali NetHunter Rootless Documentation](https://www.kali.org/docs/nethunter/nethunter-rootless/).