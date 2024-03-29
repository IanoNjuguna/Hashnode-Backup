---
title: "How to Set up Git in 3 Steps"
datePublished: Sat Feb 18 2023 18:06:37 GMT+0000 (Coordinated Universal Time)
cuid: clea9ufru000109mof80xffwl
slug: how-to-set-up-git-in-3-steps
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1676743083519/70e4aeca-18eb-44ac-970d-df75aef0ae1f.png
tags: github, programming, git, debian

---

* [Download Git](https://git-scm.com/download/linux#:~:text=Debian/Ubuntu,of%20Debian/Ubuntu) by running the following command on your terminal:
    

```Bash
$ sudo apt-get install git
```

To confirm whether your download was successful, run:

```Bash
$ git --version
```

Here's the output I got on my PC:

* [Set your username](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git) for every repository on your computer, run:
    

```Bash
$ git config --global user.name "Your-GitHub_userName"
```

To confirm that you have set the Git username correctly, run:

```Bash
$ git config --global user.name
Your-GitHub_userName
```

On my PC, the result was:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676741218772/c1cd0b2c-8406-46e0-bc43-2de10e548411.png align="center")

* [Set your commit email address](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address). This is the email address that'll be used to author commits in every repository on your computer your PC and on GitHub. This email address will be added to Git. Run the following command:
    

```Bash
$ git config --global user.email "your-email@whatever.com"
```

Confirm that you have set the email address correctly:

```Bash
$ git config --global user.email
your-email@whatever.com
```

NB: You also need to [add your email address to your GitHub account](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/adding-an-email-address-to-your-github-account).

## References

1. [Download Git](https://git-scm.com/download/linux#:~:text=Debian/Ubuntu,of%20Debian/Ubuntu)
    
2. [Set your username](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git)
    
3. [Set your commit email address](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address)