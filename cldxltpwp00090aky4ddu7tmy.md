---
title: "How to Install Google Chrome using the Linux Terminal"
seoTitle: "How to Install Google Chrome using the Linux Terminal"
seoDescription: "Open the Terminal Window. You can do this by either using the GUI or pressing CTRL + ALT + T."
datePublished: Thu Feb 09 2023 21:20:58 GMT+0000 (Coordinated Universal Time)
cuid: cldxltpwp00090aky4ddu7tmy
slug: how-to-install-google-chrome-using-the-linux-terminal
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1675974064498/dafeb5a6-649e-4c2b-97be-2da27c41727a.png
tags: linux, chrome, linux-for-beginners, linux-terminal

---

1. Open the Terminal Window. You can do this by either using the GUI or pressing `CTRL` + `ALT` + `T`.
    
2. Update and upgrade your system.  
    To do this, run the following command in your terminal:
    
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```
    
    [The `-y` flag](https://manpages.ubuntu.com/manpages/trusty/man8/apt-get.8.html), alternatively `--assume-yes` or `--yes`, automatically makes your answer to any prompts `yes`. This allows you to install packages non-interactively.
    
    If an undesirable situation occurs, such as: changing a held package, trying to install an unauthenticated package, or removing an essential package, the apt will abort.
    
    If you are unfamiliar with the commands `apt update` and `apt upgrade`, [click this](https://askubuntu.com/a/94104/1597017).
    
3. You need to confirm whether you have `wget` installed it on your PC.  
    `wget` is a tool created by the GNU project and it allows you to retrieve content and files from various web servers. To check if it's installed, run:
    
    ```bash
    wget --version
    ```
    
    If you see a version number, you are set to go.  
    If you get an error, it's because `wget` is not installed. To install `wget`, run:
    
    ```bash
    sudo apt install wget
    ```
    
4. Download the Chrome package using `wget`.  
    [There's no longer a 32-bit version of Chrome](https://support.google.com/chrome/a/answer/7100626), so we'll be installing the 64-bit version.  
    To get the latest stable version, run:
    
    ```bash
    wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
    ```
    
    Be patient while the package is downloading.
    
5. Install the Chrome package using `dpkg`.
    
    `dpkg` is the default package manager on Ubuntu. You use `dpkg` to **install, configure, upgrade, or remove packages, and retrieve information** about **these packages**.
    
    To install the Chrome package, run:
    
    ```bash
    sudo dpkg -i google-chrome-stable_current_amd64.deb
    ```
    
6. Fix the errors that occurred during installation. To do this, run:
    
    ```bash
    sudo apt-get install -f
    ```
    
7. Launch Google Chrome.  
    You have installed the browser. To launch it, you either use the GUI or run the following command in your terminal:
    
    ```bash
    google-chrome
    ```
    

### **References**

1. [https://manpages.ubuntu.com/manpages/trusty/man8/apt-get.8.html](https://manpages.ubuntu.com/manpages/trusty/man8/apt-get.8.html)
    
2. [https://askubuntu.com/questions/94102/what-is-the-difference-between-apt-get-update-and-upgrade/94104#94104](https://askubuntu.com/questions/94102/what-is-the-difference-between-apt-get-update-and-upgrade/94104#94104)
    
3. [https://www.hostinger.com/tutorials/wget-command-examples/](https://www.hostinger.com/tutorials/wget-command-examples/)
    
4. [https://support.google.com/chrome/a/answer/7100626](https://support.google.com/chrome/a/answer/7100626)