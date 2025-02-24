---
title: "Recursive Duplicates"
seoTitle: "Handle Recursive Sub-Directory Copying Effectively"
seoDescription: "Learn how to duplicate directories using `mv` and `cp` commands, including handling recursive sub-directory copying effectively"
datePublished: Mon Feb 24 2025 20:10:33 GMT+0000 (Coordinated Universal Time)
cuid: cm7jhsne3000009jpb8a24wsp
slug: recursive-duplicates
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/pDY7djN5htA/upload/7f912ca0dff4fe388786019d18fa5ece.jpeg
tags: linux

---

Let’s assume you need to create the duplicate of a directory. In this case, the directory is `dir_1` and the duplicate is `dir_2`. The quickest way to do this is by using the `mv` command to move `dir_1` and its contents to `dir_2` by virtually renaming it. Here, the `mv` command is similar to the cut utility in Windows:

```bash
$ mv /dir_1 /dir_2
```

The `mv` command isn’t useful when you need to duplicate the directory and have two copies. Then, you need to use the `cp` command but when you use the vanilla `cp` command to copy a directory with content inside of it, you get the error message below:  

```bash
cp: -r omitting directory
```

The error message means that it’s possible to copy directories but by default, the `cp` command can’t copy sub-directories in a recursive manner. To solve this, you should append a recursive flag to the command, like this:

```bash
$ cp -r /dir_1 /dir_2
```

or:

```bash
$ cp -r /dir_1 /dir_2
```

or:

```bash
cp --recursive /dir_1 dir_2
```