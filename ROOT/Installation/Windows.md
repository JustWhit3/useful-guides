# ROOT framework installation on Windows operating system

## Table of contents
- [Installation](#installation)
  * [Proceed via Windows subsystem for Linux (recommended)](#proceed-via-windows-subsystem-for-linux-recommended)
  * [Proceed via virtual machine](#proceed-via-virtual-machine)
- [Installation check](#installation-check)

## Installation

In this guide you can find two common ways of installing the C++ ROOT framework in your Windows operating system. You can proceed via [Windows subsystem for Linux](https://ubuntu.com/wsl) (recommended) if you have at least Windows 10 version, or alternatively via [virtual machine](https://www.virtualbox.org/). In both the cases be sure that your operating system is **updated**.

### Proceed via Windows subsystem for Linux (recommended)

If you have at least Windows 10 version installed you can proceed with this section, otherwise skip it and go to the next one. 

First of all you have to install the [Windows subsystem for Linux](https://ubuntu.com/wsl) (WSL) environment and a free-to-use X-server for the correct graphical visualization on the Ubuntu shell; I suggest you [MobaXterm](https://mobaxterm.mobatek.net/). Once WSL is installed, you have to open a new Ubuntu shell (go to the search pannel, type "Ubuntu" and open it) and you can finally proceed with the ROOT installation by following one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) guides I wrote. **Remember** to come back here once you have finished with them, since there is a very last passage to do to complete the procedure.

> Please remember also that if you want to see in which position of the Windows system is saved the Ubuntu subsystem you can type `explorer.exe .` (note the final dot) in the Ubuntu shell.

After the ROOT installation is completed, you need to install the packages useful for graphical visualization. Enter this command on the Ubuntu shell:
```shell
sudo apt-get install libtiff5 x11-apps
```
> You may encounter a new error `libtinfo.so.5: cannot open shared object file: No such file or directory`. In this case you can easily solve it by downloading that single library separately with this command `sudo apt-get install libncurses5`.

You have now to set the display variable. 
> If you already set this variable in the past, this last passage is not necessary and you can skip it.

Be sure of being in the `$HOME` directory:
```shell
cd $HOME
```
and open the .bashrc file:
```shell
nano .bashrc
```
> *nano* is the name of the default editor of Ubuntu, but you can also use better editors like *gedit*, *emacs*, *code* or other if you prefer.

go at the end of the file and add this two lines:
```shell
export DISPLAY="$(/sbin/ip route | awk 'default/ { print $3 }'):0"
export LIBGL_ALWAYS_INDIRECT=1
```
close the file and save it (Ctrl+X and then Ctrl+Y or Ctrl+S if you have an italian language shell). 

Now close the shell an reopen a new one and your installation is 100% completed. 

## Installation check
To check the installation run MobaXterm by clicking two times on its Windows desktop icon (you don't have to do anything else more)

Now open a new shell and type:
```shell
root
```
If the framework has been correctly installed you should see something like this:
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
Now you are able to run and compile macros. Then, enter this command in order to see if also the graphical tools work:
```shell
root [0] new TBrowser()
```
If a new window is opened then you have 100% completed the ROOT installation.

Remember that you have to run MobaXterm every time you want to use graphic interface on Ubuntu shell.

> Please note that `root [0]` indicates the line number of the ROOT command prompt in which you are writing the current ROOT bash command, therefore, from the previous line, you have to copy only `new TBrowser()` in your shell.

> In some very rare cases may happens also that some libraries are not recognized when trying to load or run a macro. You may try to solve this issue by installing the package dependencies as root user. See this [video guide](https://www.youtube.com/watch?v=nkKxNBuqsB0&t=186s).

> Sometimes it may happens that a similar error is displayed when you try to run `new TBrowser()` command in ROOT shell:
> ```shell
> Error: Can't open display: :0
> ```
> It means that your display variable is not set correctly and graphic interface doesn't work. A solution may be to replace this variable definition with the IP address of your Xserver. If you are working for example with MobaXterm, you can open it, click on "start local terminal" and copy the IP address written in "Your DISPLAY is set to..." line of the box. Than you have to open a new normal terminal and enter:
> ```shell
> export DISPLAY=XX.XX.XX.XXX:0.0
> ```
> Where `XX.XX.XX.XXX:0.0` has to be replaced with the correct IP address you copied. Remember that this solution works only for the terminal in which you are working in. If you close the shell and open a new one, you have to repeat this very last passage. In this particular situation, avoid copying the previous command in the .bashrc file, since if your IP address changes, than you have to modify the .bashrc file every time.

> Sometimes also this latter case doesn't solve the problem. In this situation you can try to install a different free-to-use X-server like [Xming](https://sourceforge.net/projects/xming/) or [VcXsrv](https://sourceforge.net/projects/vcxsrv/). 
> Check also if you are trying to run commands as user and not as root; enter on the shell:
> ```shell
> whoami
> ```
> If `root` is displayed than you have to switch from *root* user to the real user of your machine; supposing the real user is called *name* you can do it by typing:
> ```shell
> su - name
> ```

### Proceed via virtual machine

In this case you need to install a [virtual machine](https://www.virtualbox.org/) on Windows (not so easy). Once you have done this, you can run it and follow one of the [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md) installation instructions.
