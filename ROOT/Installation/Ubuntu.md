# ROOT framework installation on Ubuntu operating system

## Table of contents
- [Installation](#installation)
  * [Proceed via binary distribution (warmly recommended)](#proceed-via-binary-distribution-warmly-recommended)
  * [Proceed via source code](#proceed-via-source-code)
  * [Other installation methods (not recommended)](#other-installation-methods-not-recommended)
- [Installation check](#installation-check)

## Installation

In this guide you can find some common ways of installing the C++ ROOT framework in your MacOS operating system. There are many ways to proceed with the installation, however I warmly suggest you yo install Ubuntu via binary distribution, since this is the simpler and most efficient method to get the framework in your machine. Alternatively, and in case you cannot solve issues any way with binary installation, you have first to [uninstall](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Uninstall.md) the software and then to proceed with other installation possibilities: I suggest you first to try to buil ROOT from source code and if also this doesn't work (very unlikely) you can try alternative ways (try to avoid them if possible).

Before choosing the installation method you have firstly to update your operating system, in order to be sure that all programs are correctly updated for the procedure. Open a fresh shell and type this two commands:
```shell
sudo apt-get upgrade
sudo apt-get update
```
After the system has been updated, decide in which folder you want to install ROOT and enter it.
> If you want to install it in the `home` directory you don't have to do anything, just open a shell and continue with the following steps. Instead, if you want to install it for example in a folder named `dir`, which is located in `path/to/directory` path, you have to type `cd path/to/directory/dir` first, and then proceed with the guide.

### Proceed via binary distribution (warmly recommended)



### Proceed via source code

### Other installation methods (not recommended)

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
