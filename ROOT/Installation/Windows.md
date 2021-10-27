# ROOT framework installation on Windows operating system

## Table of contents
- [Installation](#installation)
  * [Windows subsystem for Linux](#winwdows-subsystem-for-linux)
  * [Virtual machine](#virtual-machine)

## Installation

In this guide you can find two common ways of installing the C++ ROOT framework in your Windows operating system. You can proceed via [Windows subsystem for Linux](https://ubuntu.com/wsl) (recommended) if you have at least Windows 10 version or alternatively via [virtual machine](https://www.virtualbox.org/). In both these cases be sure that your operating system is updated.

### Windows subsystem for Linux

If you have at least Windows 10 version installed you can proceed with this section, otherwise skip this section and go to the next one. 

First of all you have to install on Windows [Windows subsystem for Linux](https://ubuntu.com/wsl) and a free-to-use X-server for the correct graphical visualization on the Ubuntu shell, I suggest you [Xming](https://sourceforge.net/projects/xming/). Then, you have to open a new Ubuntu shell (go to the search pannel, type "Ubuntu" and open it) and you can finally proceed with the ROOT installation by following one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) guides I wrote.

> Please remember that if you want to see in which position of the Windows system is saved the Ubuntu subsystem you can type `explorer.exe .` in the Ubuntu shell.

After the ROOT installation is completed, you need to install the packages useful for graphical visualization; type this on the Ubuntu shell:
```shell
sudo apt-get install libtiff5 x11-apps
```
You have now to set the display variable: be sure of being in the `home` directory (type `cd` command in a fresh shell if you need) and open the .bashrc file:
```shell
editor .bashrc
```
> Editor is the name of the editor you want to use to open the file (you can use nano, *gedit*, *emacs*, *code* or whatever you prefer; as a default use nano).

go at the end of the file and add this line:
```shell
export DISPLAY=:0
```
close the file and save it (Ctrl+X and then Ctrl+Y or Ctrl+S if you have an italian language shell). Now close the shell an reopen a new one and your installation is 100% completed. 

To check it: run Xming by clicking two times on its Windows desktop icon (don't worry if nothing happens, it is normal) and follow the "Installation check" part of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) installation guide to check if ROOT works correctly.
> Remember that you have to run Xming every time you want to use graphic interface on Ubuntu shell.

Sometimes it may happens that an error is displayed

### Virtual machine

In this case you need to install a [virtual machine](https://www.virtualbox.org/) on Windows. Once you have done this, you can run it and follow one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) installation instructions.
