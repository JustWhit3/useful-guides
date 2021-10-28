# ROOT framework installation on Windows operating system

## Table of contents
- [Installation](#installation)
  * [Proceed via Windows subsystem for Linux (recommended)](#proceed-via-winwdows-subsystem-for-linux-recommended)
  * [Proceed via virtual machine](#proceed-via-virtual-machine)

## Installation

In this guide you can find two common ways of installing the C++ ROOT framework in your Windows operating system. You can proceed via [Windows subsystem for Linux](https://ubuntu.com/wsl) (recommended) if you have at least Windows 10 version or alternatively via [virtual machine](https://www.virtualbox.org/). In both these cases be sure that your operating system is updated.

### Proceed via Windows subsystem for Linux (recommended)

If you have at least Windows 10 version installed you can proceed with this section, otherwise skip this section and go to the next one. 

First of all you have to install on Windows [Windows subsystem for Linux](https://ubuntu.com/wsl) and a free-to-use X-server for the correct graphical visualization on the Ubuntu shell, I suggest you [MobaXterm](https://mobaxterm.mobatek.net/). Then, you have to open a new Ubuntu shell (go to the search pannel, type "Ubuntu" and open it) and you can finally proceed with the ROOT installation by following one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) guides I wrote, but come back here once you have finished with them, since there is a very last passage to do.

> Please remember that if you want to see in which position of the Windows system is saved the Ubuntu subsystem you can type `explorer.exe .` (note the final dot) in the Ubuntu shell.

After the ROOT installation is completed, you need to install the packages useful for graphical visualization; type this on the Ubuntu shell:
```shell
sudo apt-get install libtiff5 x11-apps
```
You have now to set the display variable: be sure of being in the `$HOME` directory:
```shell
cd $HOME
```
and open the .bashrc file:
```shell
nano .bashrc
```
> `nano` is the name of the default editor of Ubuntu. You can also use better editors like *gedit*, *emacs*, *code* or whatever you prefer.

go at the end of the file and add this line:
```shell
export DISPLAY=:0
```
close the file and save it (Ctrl+X and then Ctrl+Y or Ctrl+S if you have an italian language shell). Now close the shell an reopen a new one and your installation is 100% completed. 

To check it: run MobaXterm by clicking two times on its Windows desktop icon (you don't have to do anything else more) and follow the "Installation check" part of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) installation guide to check if ROOT works correctly. Remember that you have to run MobaXterm every time you want to use graphic interface on Ubuntu shell.
> Sometimes it may happens that a similar error is displayed when you try to run `new TBrowser()` command in ROOT shell:
> ```shell
> Error: Can't open display: :0
> ```
> It means that your display variable is not set correctly and graphic interface doesn't work. A solution may be to replace this definition in the .bashrc file with:
> ```shell
> export DISPLAY=localhost:0.0
> ```
> in order to configure bash to use the local X-server. If also this doesn't work you can try to set the X-server IP address which could be found here `/ets/resolv/conf` by replacing the previous command with:
> ```shell
> export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
> ```
> Sometimes also this latter case doesn't solve the problem. In this situation you can try to install a different free-to-use X-server like [Xming](https://sourceforge.net/projects/xming/) or [VcXsrv](https://sourceforge.net/projects/vcxsrv/). Check also if you are trying to run commands as user and not as root: type:
> ```shell
> whoami
> ```
> If 
> ```shell
> root
> ```
> is displayed you have to switch from *root* user to the real user of your machine; supposing the real user is called *name* you can do it by typing:
> ```shell
> su - name
> ```

### Proceed via virtual machine

In this case you need to install a [virtual machine](https://www.virtualbox.org/) on Windows (not so easy). Once you have done this, you can run it and follow one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) installation instructions.
