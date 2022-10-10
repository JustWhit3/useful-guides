# ROOT framework installation on MacOS operating system

## Table of contents
- [Shell script installer](#shell-script-installer)
- [Installation](#installation)
  * [Proceed via brew (recommended)](#proceed-via-brew-recommended)
  * [Proceed via MacPorts](#proceed-via-macports)
- [Installation check](#installation-check)

## Shell script installer

Before talking about the real guide, I want to inform you that I developed a shell script that automatically install the ROOT framework in your computer, by only entering just a command in the terminal command prompt! This script is available for Ubuntu, Windows and MacOS operating systems and fully supports many of the common installation methods (binary, source, package manager etc...). You can find more information and instructions about how to use it [here](https://github.com/JustWhit3/root-framework-installer). If you prefer to install the framework manually and to check step-by-step passages during the installation (recommended), therefore you can continue with the following guide.

## Installation

In this guide you can find two common ways of installing the C++ ROOT framework in your MacOS operating system. You can proceed via [brew](https://brew.sh/index_it) package manager (recommended) or alternatively via [MacPorts](https://www.macports.org/).

Before choosing the installation method you have firstly to update your operating system, in order to be sure that all programs are correctly updated for the procedure. Open a fresh shell and type:
```shell
softwareupdate --install -a
```
After the system has been updated, decide in which folder you want to install ROOT and enter it throught the shell.

> :warning: If you want to install it in the `$HOME` directory you don't have to do anything, just open a shell and continue with the following steps. Instead, if you want to install it for example in a `dir` folder, which is located in `path/to/directory` path, you have to type `cd path/to/directory/dir` first, and then proceed with the guide. I recommend you to install it in the `$HOME` directory.

### Proceed via brew (recommended)

You can now continue with brew package manager installation (if you have already installed brew you can skip this passage):

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> :warning: Pay attention to old guides which use this link: https://raw.githubusercontent.com/Homebrew/install/master/install. It doesn't work anymore, therefore DON'T run the previous command with this broken link.

Now you can update and upgrade brew packages with (enter the commands one after the other):

```shell
brew update
brew upgrade
```

Now you can finally install root with:

```shell
brew install root
```

> :warning: If you get errors after ROOT installation or in the `brew upgrade` passage you probably forgot to update your system with `softwareupdate --install -a` command.

### Proceed via MacPorts

First, you have to install Xcode developer package:

```shell
xcode-select --install
```

Then, you can install [MacPorts](https://www.macports.org/) by clicking on the link and following the guide. 

Finally you have to type this command:

```shell
port install root6
```

## Installation check

Once tou have installed root, you need to check if all the features have been correctly installed. Close the current shell and reopen a new one and type:

```shell
root
```

If the framework has been installed correctly you should see something like this in the command prompt:

```shell
   ------------------------------------------------------------------
  | Welcome to ROOT 6.20/02                        https://root.cern |
  | (c) 1995-2020, The ROOT Team; conception: R. Brun, F. Rademakers |
  | Built for linuxx8664gcc on Sep 22 2021, 10:57:00                 |
  | From tag , 15 March 2020                                         |
  | Try '.help', '.demo', '.license', '.credits', '.quit'/'.q'       |
   ------------------------------------------------------------------

root [0] 
```

Now you are able to run macros and compile codes. To check if also the graphical tools work type this:

```shell
root [0] new TBrowser()
```

If a new window is opened then you have 100% completed the ROOT installation.

> :warning: Please note that `root [0]` indicates the line number of the ROOT command prompt in which you are writing the current ROOT bash command, therefore, from the previous line, you have to copy only `new TBrowser()` in your shell.
