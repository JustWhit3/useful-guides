# ROOT framework installation on MacOS operating system

## Table of contents
- [Installation](#installation)
  * [Proceed via brew (recommended)](#proceed-via-brew-recommended)
  * [Proceed via MacPorts](#proceed-via-macports)
- [Installation check](#installation-check)

## Installation

In this guide you can find two common ways of installing the C++ ROOT framework in your MacOS operating system. You can proceed via [brew](https://brew.sh/index_it) package manager (recommended) or alternatively via [MacPorts](https://www.macports.org/).

Before choosing the installation method you have firstly to update your operating system, in order to be sure that all programs are correctly updated for the procedure. Open a fresh shell and type:
```shell
softwareupdate -l
```
After the system has been updated, decide in which folder you want to install ROOT and enter it.
> If you want to install it in the `home` directory you don't have to do anything, just open a shell and continue with the following steps. Instead, if you want to install it for example in a folder named `dir`, which is located in `path/to/directory` path, you have to type `cd path/to/directory/dir` first, and then proceed with the guide.

### Proceed via [brew](https://brew.sh/index_it) (recommended)

You can now continue with brew package manager installation:
> If you have already installed brew you can skip this passage.
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
> Pay attention to old guides which use this link: https://raw.githubusercontent.com/Homebrew/install/master/install. It doesn't work anymore, therefore DON'T run the previous command with this broken link.

Now you can update and upgrade brew packages with (enter the commands one after the other):
```shell
brew updated
brew upgrade
```
Now you can finally install root with:
```shell
brew install root6
```

### Proceed via [MacPorts](https://www.macports.org/)

First, you have to install Xcode developer package:
```shell
xcode-select --install
```
Then, you can install [MacPorts](https://www.macports.org/) by clicking on the link and following the guide. And finally you have to type this command:
```shell
port install root6
```

## Installation check

Once tou have installed root, you need to check if all the features have been correctly installed. Close the current shell and reopen a new one and type:
```shell
root
```
If the framework has been installed you should see something like this:
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
then, type this command in order to see if also the graphical tools work:
```shell
root [0] new TBrowser()
```
If a new window is opened then you have 100% completed the ROOT installation
> Please note that `root [0]` indicates the line number of the ROOT command prompt in which you are writing the current ROOT bash command, therefore, from the previous line, you have to copy only `new TBrowser()` in your shell.
