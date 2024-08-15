+++
title = "Why Doom Emacs is a Cool Emacs Config"
author = ["Kameron"]
date = 2024-07-30T00:00:00-07:00
draft = true
+++

## Introduction to Emacs {#introduction-to-emacs}

GNU Emacs is an open source, customizable graphical text editor with different modes[^fn:1]. GNU Emacs is usually just called Emacs, which is what I will call it from now on.


### Orgins {#orgins}

It was originally a Terminal application, but it was different than other text editors from the time since it had a User Interface.


### Differences {#differences}

Some people may think that Emacs is a graphical clone of Vim, but that's actually a plugin that makes it more like Vim (more on that later). Standard Emacs is more like VSCode in terms of controlling, but it came _way_ before VSCode. It doesn't have a Normal mode or Insert mode, it's just like VSCode where when you type it puts it in the file. There are still keybinds though. If you press Alt+x (referred to as M-x, M means Meta). It opens up a command prompt similar to Vim's Command Mode.


### Church and Cult {#church-and-cult}

Remember how earlier in this post there is a Vim plugin for Emacs? Its name is `evil-mode`. Because of the name usually people who use the standard Emacs keybinds are in the church of Emacs, while people who use Vim Keybinds are in the cult of Vim. Don't get scared and stick to using Emacs keybinds when you are used to Vim keybinds. It's just a silly thing that Emacs users do.


## Doom Emacs {#doom-emacs}

Doom Emacs is a config for Emacs.

> An Emacs framework for the stubborn martian hacker.
>
> -   the Doom Emacs description on it's code page

It's designed to be fast and as close to base Emacs as possible. It also has a Command Line Interface `doom`. Doom Emacs _is_ designed for Linux and Mac, but it can be used with Windows (I've tried it before, but I don't recommend. If you want to use it with Windows, use it in a Linux virtual machine, like Microsoft's WSL.).


### Defaults and Package Management {#defaults-and-package-management}

Doom Emacs defaults to using `evil-mode`, so it's Vim user friendly. Doom Emacs has a `init.el` file in its config for packages that have code in Doom Emacs that supports it. If you can't find a package you want to use in that file, you can install it in the `packages.el` file.


#### Init File {#init-file}

There are multiple sections of the init file.
You can uncomment lines to activate them. Make sure to save before reloading your config.
You can learn more about a package by pressing K if you are using `evil-mode` or Control+C+c+k if you use the standard Emacs keybinds (Control+C will **NOT** close your editor, unlike other apps where Control+C will).
If you want to add a Module Flag to the package, first surround it with parentheses (ex. `(package)`), then add the module flag (ex. `(package +flag)`).

<!--list-separator-->

-  :input

    This section allows you to setup things relating to your keyboard to make using Doom Emacs easier if you are not using America's `QWERTY` layout.

<!--list-separator-->

-  :completion

    For a normal user, you do not need to change things (unless you want to add some `+icons` to `vertico`). If you do want to change your completions, go ahead.

<!--list-separator-->

-  :ui

    This changes the User Interface of Doom Emacs, or adds new User Interfaces to it. It can also add features like for example, `deft`. It is known as a Major Mode, and it is meant for creating, browsing, and filtering notes.
    You can also add some `tabs` to it.

<!--list-separator-->

-  :editor

    This allows you to add more features to the text editor part of Emacs. If you want to have multiple cursors like you can have in VSCode, uncomment `multiple-cursors`.

<!--list-separator-->

-  :emacs

    This makes built-in Emacs features nicer. Not much for this.

<!--list-separator-->

-  :term

    This makes it so you can have a terminal in Emacs. I (and many others including the config) recommend you use `vterm`.

    > the best terminal emulation in Emacs
    >
    > -   Doom Emacs comment in its config

<!--list-separator-->

-  :checkers

    These are for checking your code mistakes, and/or your grammar mistakes, and/or your spelling mistakes.
    `syntax` is not needed for error detection (another plugin does it), but it's recommended for error highlighting for easier error spotting without using the search tool a lot.

<!--list-separator-->

-  :tools

    This section is really important if you are looking to code in Doom Emacs.

    -   `lsp` is for showing errors, and other cool actions like if you were using VSCode.
    -   `tree-sitter` This isn't required, but if you want _actually good_ syntax highlighting, uncomment this.

    The issue with both is that if you want to _use_ them, you have to enable it for each language you want to use them on. More on that in the :lang section.

    If you use git, you should enable `magit`, it's a great git manager for Emacs.

<!--list-separator-->

-  :os

    This is for supporting other ways of using Emacs.

    -   `macos` is to enable more support for MacOS. You shouldn't have to enable it since it does it automatically.
    -   `tty` is for better terminal support, if you don't have a Desktop Enviroment or Window Manager, or if you like using Emacs like it was like the early days.

<!--list-separator-->

-  :lang

    This section is for enabling programming language support.

    Most of them should support these two options:

    -   Language Servers `+lsp`, requires `lsp` to be enabled in :tools.
    -   Better Syntax Highlighting `+tree-sitter`, requires `tree-sitter` to be enabled in :tools.

<!--list-separator-->

-  :email

    If you want to use Emacs as an Email Client, you can enable one of these. I don't use them so I don't have anything to say about them.

<!--list-separator-->

-  :app

    There are some apps for Emacs. You can enable some here.

<!--list-separator-->

-  :config

    There are two options for your config.

    -   `literate` uses Org Mode for turning your config into documentation.
    -   `default` is for Doom Emacs defaults. If you are not a Pro User, leave it alone.


#### Config File {#config-file}

The config file is for configuring variables, packages, and Doom Emacs.

[^fn:1]: Basically plugins that do different things with Emacs.
