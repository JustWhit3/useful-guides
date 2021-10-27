# ROOT framework installation on Windows operating system

## Table of contents
- [Installation](#installation)
  * [Windows subsystem for Linux](#proceed-via-winwdows-subsystem-for-linux)
  * [Virtual machine](#proceed-via-virtual-machine)
- [Installation check](#installation-check)

## Installation

In this guide you can find two common ways of installing the C++ ROOT framework in your Windows operating system. You can proceed via [Windows subsystem for Linux](https://github.com/giacomini/pf2021/blob/main/doc/WSLGuide.md) (recommended) if you have at least Windows 10 version or alternatively via [virtual box](https://www.virtualbox.org/).

In both the cases be sure that your operating system is updated.

### Windows subsystem for Linux

In this case you have to install [Windows subsystem for Linux](https://github.com/giacomini/pf2021/blob/main/doc/WSLGuide.md) on you computer and a free-to-use X-server for the correct graphical visualization on the Ubuntu shell, I suggest you [Xming](https://sourceforge.net/projects/xming/). Than you have to open a new Ubuntu shell (go to the search pannel, type "Ubuntu" and open it). Now you can proceed with the ROOT installation by following one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) guides I wrote.

> Please remember that if you want to see in which position of the Windows system is saved the Ubuntu subsystem you can type `explorer.exe .` in the Ubuntu shell.

Now, to install the packages useful for graphic visualization you can type this commands:
```shell
sudo apt-get install libtiff5 x11-apps
```
Than you have to set the display variable. Be sure to be in the `home` directory (press `cd` if you need)
