# ROOT framework installation on Windows operating system

## Table of contents
- [Installation](#installation)
  * [Windows subsystem for Linux](#proceed-via-winwdows-subsystem-for-linux)
  * [Virtual machine](#proceed-via-virtual-machine)
- [Installation check](#installation-check)

## Installation

In this guide you can find two common ways of installing the C++ ROOT framework in your Windows operating system. You can proceed via [Windows subsystem for Linux](https://github.com/giacomini/pf2021/blob/main/doc/WSLGuide.md) (recommended) if you have at least Windows 10 version or alternatively via [virtual machine](https://www.virtualbox.org/).

In both the cases be sure that your operating system is updated.

### Windows subsystem for Linux

Be sure to have at least Windows 10 version installed and than you can proceed, alternatively, skip this section and go to the next one. 

First of all you have to install [Windows subsystem for Linux](https://github.com/giacomini/pf2021/blob/main/doc/WSLGuide.md) on you computer and a free-to-use X-server for the correct graphical visualization on the Ubuntu shell, I suggest you [Xming](https://sourceforge.net/projects/xming/). Than you have to open a new Ubuntu shell (go to the search pannel, type "Ubuntu" and open it). Now you can proceed with the ROOT installation by following one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) guides I wrote.

> Please remember that if you want to see in which position of the Windows system is saved the Ubuntu subsystem you can type `explorer.exe .` in the Ubuntu shell.

Now, to install the packages useful for graphic visualization you can type this commands:
```shell
sudo apt-get install libtiff5 x11-apps
```
Than you have to set the display variable: be sure of being in the `home` directory (press `cd` if you need) and open the .bashrc file:
```shell
editor .bashrc
```
> Editor is the name of the editor you want to use to open it (you can use nano, gedit, emacs, code or whatever you prefer).

Go at the end of the file and add this line:
```shell
export DISPLAY=:0
```
Close the file and save it (Ctrl+X and than Ctrl+Y or Ctrl+S if you have an italian language shell). Now your installation is finished. 

Open Xming by clicking two times on its icon (don't worry if nothing happens, it is normal) and follow the "Installation check" part of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) installation guide to check if ROOT works correctly.

### Virtual machine

In this case you need to install a [virtual machine](https://www.virtualbox.org/) on Windows. Once you have done this you can run it and follow the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) installation instructions.
