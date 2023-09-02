---
title: "How I Set Up My Neovim Config For Web Development"
seoTitle: "Set Up Neovim For Web Development"
seoDescription: "Set Up NeoVim For Web Development"
datePublished: Sat Sep 02 2023 19:55:08 GMT+0000 (Coordinated Universal Time)
cuid: clm2g0ydf000609jvbgtrfpdj
slug: how-i-set-up-my-neovim-config-for-web-development
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693684410963/20512a6c-8dd0-496a-998b-86fc2051b70f.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693684464377/d0be59e5-8c97-4b8f-9458-32c6514d3c83.png
tags: web-development, vim, neovim, webdev, vim-linux

---

## Introduction

I've been using the Neovim text editor for the past year.

While I still rely on VS Code for certain tasks, my journey with Neovim has been enjoyable.

In this guide, I'll walk you through how I've set up my Neovim configuration to boost my web development workflow.

To begin with, you need the following software installed on your PC:

* **The** [**Neovim**](https://neovim.io/) **text editor.**
    
* **Node and npm****: they provide** a JS runtime for the CoC extension.
    
* **The** [**vim-plug**](https://github.com/junegunn/vim-plug) **plugin manager**
    
* [**Git**](https://git-scm.com/)**: allow** vim-plug to clone the plugins on GitHub
    

## The `init.vim` file

Create an `init.vim` in the `~/.config/nvim/` directory.

This is a configuration file used to customize the behavior and appearance of the text editor. It allows a user to define various settings, keybindings, plugins, and other preferences to tailor the text editor to their specific needs.

Insert the following VimScript code in your init.vim file:

```abap
" this will install vim-plug if not installed
if empty(glob('~/.config/nvim/autoload/plug.vim'))
    silent !curl -fLo ~/.config/nvim/autoload/plug.vim --create-dirs
        \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
    autocmd VimEnter * PlugInstall
endif
    
call plug#begin()
" here you'll add all the plugins needed
    
call plug#end()
```

This code instructs Neovim to download and install vim-plug on launch.

All the plugins between the `plug#begin()` and `plug#end` lines will be installed with the `:PlugInstall` command.

## The plugins

In the `init.vim` file, add the following between `plug#begin()` and `plug#end()`:

```abap
" Add IDE functionality to NeoVim
Plug 'neoclide/coc.nvim', {'do': 'yarn install --frozen-lockfile'} 

let g:coc_global_extensions = ['coc-tslint-plugin', 'coc-tsserver', 'coc-eslint', 'coc-html-css-support', 'coc-rome', 'coc-tsserver', 'coc-css', 'coc-html', 'coc-json', 'coc-prettier']  

" Auto Close Brackets ( [ {
Plug 'jiangmiao/auto-pairs' 

" Add Highlighting and Indenting to JSX and TSX files.
Plug 'yuezk/vim-js'
Plug 'HerringtonDarkholme/yats.vim'
Plug 'maxmellon/vim-jsx-pretty'
```

Save and exit the file, then re-open it.

Type `:PlugInstall` to install the plugins and extensions.

## Conclusion

Check out this GitHub repository for more ideas on how you can customise Neovim to your liking:

%[https://github.com/IanoNjuguna/dotfiles]