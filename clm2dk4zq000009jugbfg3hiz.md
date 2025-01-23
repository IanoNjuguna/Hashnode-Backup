---
title: "How to Install the Latest Version of Ruby in Ubuntu 22.04"
seoTitle: "Install Ruby in Ubuntu (Linux)"
seoDescription: "Install Ruby in Ubuntu or Linux OS"
datePublished: Sat Sep 02 2023 18:46:04 GMT+0000 (Coordinated Universal Time)
cuid: clm2dk4zq000009jugbfg3hiz
slug: how-to-install-ruby-in-ubuntu
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/p8w7krXVY1k/upload/3d47de9c60c64c2fec2b1c935a75063a.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694458314903/b21697e0-5f4b-45ab-8be1-24fe401041de.png
tags: ubuntu, ruby, ubuntu-2204

---

## Introduction

Naturally, Rubies are one of the [four precious gemstones](https://en.wikipedia.org/wiki/Gemstone#Characteristics_and_classification) and the name comes from the Latin word `rubens` meaning red. Rubies are beautiful, hard and durable - second only to moissanite and diamonds on the [Mohs Scale of Hardness](https://youtu.be/hiNpZqhcQEI?si=9iMU0C4w0SNgi4Yt).

In the programming world, Ruby is a multi-paradigm programming language. It is interpreted, high-level, and general-purpose. The development of the language was done by [Yukihiro Matsumoto](https://en.wikipedia.org/wiki/Yukihiro_Matsumoto) in Japan during the 1990s.

This tutorial will guide you on how to install the latest version of Ruby. If you are developing Ruby applications and working in multiple Ruby environments, this is the preferred way to go about it.

## **What is the** `RVM` ?

[Ruby Version Manager(`RVM`)](https://rvm.io/rvm/install) is a command-line tool that allows you to easily install, manage, and work with multiple Ruby environments.

It installs different versions of Ruby locally for the user and updates environment variables for Ruby and `gems` based on which version you decide to use.

`RubyGems i.e. gems`, are libraries that you can install and use in every project on your server.

If you make some code that you like to share, you can make a gem or plugin of it. Then publish it on version control platforms such as [GitHub.com](https://github.com/rubygems/rubygems)

RVM supports most UNIX-like systems and Windows (with [**Cygwin**](https://cygwin.com/) or [**Bash on Ubuntu on Windows**](https://msdn.microsoft.com/en-us/commandline/wsl/about)). The basic requirements are `bash`, `curl`, `gpg2` and overall GNU version of tools - but RVM tries to autodetect it and install anything that is needed.

### Installing the most stable Ruby version

Install the dependencies required to build Ruby from `source`:

```bash
sudo apt update
```

```bash
sudo apt install curl g++ gcc autoconf automake bison libc6-dev \        libffi-dev libgdbm-dev libncurses5-dev libsqlite3-dev libtool \        libyaml-dev make pkg-config sqlite3 zlib1g-dev libgmp-dev \        libreadline-dev libssl-dev
```

Run the following commands to add the GPG keys and install RVM:

```bash
curl -sSL https://rvm.io/mpapis.asc | gpg --import -
```

```bash
curl -sSL https://rvm.io/pkuczynski.asc | gpg --import -
```

```bash
curl -sSL https://get.rvm.io | bash -s stable
```

To start using RVM, load the script environment variables using the [`source`](https://linuxize.com/post/bash-source-command/) command:

```bash
source ~/.rvm/scripts/rvm
```

To get a list of all Ruby versions that can be installed with this tool, type:

```bash
rvm list known
```

Install the latest stable version of Ruby with RVM and set it as the default version:

```bash
rvm install ruby
```

```bash
rvm --default use ruby
```

Verify that Ruby was properly installed by printing the version number:

```bash
ruby -v
```

```bash
# OUTPUT (2nd SEPTEMBER 2022)
ruby 3.0.2p107 (2021-07-07 revision 0db68f0233) [x86_64-linux-gnu]
```

From the Output:

* Ruby Version: 3.0.2p107
    
* Release Date: July 7, 2021
    
* Architecture: x86\_64-linux-gnu
    

> This information tells us that Ruby version 3.0.2 is installed on a 64-bit Linux system.

### Installing a specific Ruby Version

If you want to install a specific version of Ruby, enter the commands below:

Get a list of all Ruby versions that can be installed with `RVM`:

```bash
rvm list known
```

Replace `x.x.x` with the Ruby version you want to install:

```bash
rvm install ruby-x.x.x
```

Make the installed Ruby version default:

```bash
rvm --default use ruby-x.x.x
```

To switch to another version without setting it as your default Ruby, enter:

```bash
rvm use ruby-x.x.x
```

## Conclusion

The `RVM` scripts give you more flexibility to use different Ruby versions on a per-user basis.