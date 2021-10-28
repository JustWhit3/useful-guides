# ROOT framework installation on Ubuntu operating system

## Table of contents
- [Installation](#installation)
  * [Proceed via binary distribution (warmly recommended)](#proceed-via-binary-distribution-warmly-recommended)
  * [Proceed via source code](#proceed-via-source-code)
  * [Other installation methods (not recommended)](#other-installation-methods-not-recommended)
- [Installation check](#installation-check)

## Installation

In this guide you can find some common ways of installing the C++ ROOT framework in your MacOS operating system. There are many ways to proceed with the installation, however I **warmly** suggest you yo install Ubuntu via binary distribution, since this is the simpler and most efficient method to get the framework in your machine. Alternatively, and in case you cannot solve issues any way with binary installation, you have first to [uninstall](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Uninstall.md) the software and then to proceed with other installation possibilities: I suggest you first to try to buil ROOT from source code and if also this doesn't work (very unlikely) you can try alternative ways (try to avoid them if possible).

Before choosing the installation method you have firstly to update your operating system, in order to be sure that all programs are correctly updated for the procedure. Open a fresh shell and type this two commands:
```shell
sudo apt-get upgrade
sudo apt-get update
```
After the system has been updated, decide in which folder you want to install ROOT and enter it through the shell.
> If you want to install it in the `home` directory you don't have to do anything, just open a shell and continue with the following steps. Instead, if you want to install it for example in a folder named `dir`, which is located in `path/to/directory` path, you have to type `cd path/to/directory/dir` first, and then proceed with the guide.

First of all you have to install all the prerequisite packages. Mandatory are (type the following command on the shell):
```shell
sudo apt-get install git dpkg-dev cmake g++ gcc binutils libx11-dev libxpm-dev libxft-dev libxext-dev
```
Other not mandatory, but suggested packages to install are:
```shell
sudo apt-get install gfortran libssl-dev libpcre3-dev xlibmesa-glu-dev libglew1.5-dev libftgl-dev libmysqlclient-dev libfftw3-dev libcfitsio-dev graphviz-dev libavahi-compat-libdnssd-dev libldap2-dev python-dev libxml2-dev libkrb5-dev libgsl0-dev libqt4-dev
```
> Please note that it is warmly suggested to install also the prerequisite packages in order to avoid encountering future ROOT errors about libraries paths not found.

### Proceed via binary distribution (warmly recommended)

Once you have completed the prerequisites you can proceed with the real installation. As previously mentioned, this is (in my opinion) maybe the most efficient and intuitive way to install the ROOT framework. First of all you have to download the release from this [link](https://root.cern/install/all_releases/); click on the latest release button and choose the binary distribution corresponding to your operating system version.
> To know the operating system version of your computer simply type this command on the shell: `lsb_release -a`.

> If you are installing ROOT in an Ubuntu shell of Windows you can type this command on the Ubuntu shell `explorer.exe .` (note the final dot) in order to know in which position of the Windows system is stored the Ubuntu folder. Then you can copy manually the downloaded ROOT folder from Windows to the Ubuntu previously mentioned folder.
Once the zipped folder is downloaded you have to move it from the download section to the home:
```shell
mv $HOME/Download/root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar.gz $HOME/.
```
where `Downloads` can be replaced with the name of the download folder of your computer (in italian usually is `Scaricati`).
> Pay attention that `root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar.gz` have to be replaced with the name of the version you are installing. For example if you are installing the Ubuntu 20 binary it would be something like `root_v6.24.06.Linux-ubuntu20-x86_64-gcc9.3.tar.gz`.
Now unzip it by typing this two commands:
```shell
gunzip root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar.gz
tar -xvf root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar
```
> Remember again to replace the `x` with the version numbers.
Ok, now if you enter:
```shell
ls
```
you can see that, among all the folders of your system there is also a new one called `root`. To complete the installation you have to set up the ROOT environment; in order to avoid repeating this latter command every time you enter the shell, you can do the following passages. Go in the `$HOME` directory:
```shell
cd $HOME
```
and open the .bashrc file:
```shell
nano .bashrc
```
> `nano` is the name of the default editor of Ubuntu. You can also use better editors like *gedit*, *emacs*, *code* or whatever you prefer.
Go at the end of the file and add this line:
```shell
source root/bin/thisroot.sh
```
> Please pay attention: if you planned to install ROOT in a different directory from the `$HOME` one, you have to replace the above command with `source path/to/folder/root/bin/thisroot.sh` where `path/to/folder/` is the path to the folder in which you installed ROOT previously.
Now close the file and save it (Ctrl+X and then Ctrl+Y or Ctrl+S if you have an italian language shell). Close also the shell an reopen a new one and your installation is 100% completed. 

### Proceed via source code

Another way to install ROOT is via source code. This is another good way to install ROOT, but since it is more complicated with respect to previous one, I suggest you to try this only in case the other one fails in any ways.

Once you have completed the prerequisites you can proceed with the installation. First of all you have to download the release from this [link](https://root.cern/install/all_releases/); click on the latest release button and choose the source distribution link for download.
> If you are installing ROOT in an Ubuntu shell of Windows you can type this command on the Ubuntu shell `explorer.exe .` (note the final dot) in order to know in which position of the Windows system is stored the Ubuntu folder. Then you can copy manually the downloaded ROOT folder from Windows to the Ubuntu previously mentioned folder.
Once the zipped folder is downloaded you have to move it from the download section to the home:
```shell
mv $HOME/Downloads/root_vx.xx.xx.source.tar.gz
$HOME/.
```
where `Downloads` can be replaced with the name of the download folder of your computer (in italian usually is `Scaricati`).
> Pay attention that `root_vx.xx.xx.source.tar.gz` have to be replaced with the name of the version you are installing. For example if you are installing the latest version it would be something like `root_v6.24.06.source.tar.gz`.
Now unzip it, by typing this two commands:
```shell
gunzip root_vx.xx.xx.source.tar.gz
tar -xvf root_vx.xx.xx.source.tar.tar
```
> Remember again to replace the `x` with the version numbers.
Ok, now if you enter:
```shell
ls
```
you can see that, among all the folders of your system there is also a new one called `root-x.xx.xx` with the version numbers instead of `x`.

Now you have to do the following passages:
a) Create a build directory:
```shell
mkdir root-build
```
and enter it:
```shell
cd root-build
```
Configure it:
```shell
cmake $HOME/root-x.xx.xx
```
> Please pay attention: if you planned to install ROOT in a different directory from the `$HOME` one, you have to replace the above command with `cmake path/to/folder/root-x.xx.xx` where `path/to/folder/` is the path to the folder in which you downloaded ROOT previously.
Compile it (this will take a while):
```shell
cmake --build .
```
To complete the installation you have to set up the ROOT environment; in order to avoid repeating this latter command every time you enter the shell, you can do the following passages. Go in the `$HOME` directory:
```shell
cd $HOME
```
and open the .bashrc file:
```shell
nano .bashrc
```
> `nano` is the name of the default editor of Ubuntu. You can also use better editors like *gedit*, *emacs*, *code* or whatever you prefer.
Go at the end of the file and add this line:
```shell
source root-x.xx.xx/bin/thisroot.sh
```
> Again remember to replace the `x`.

> Please pay attention: if you planned to install ROOT in a different directory from `$HOME`, you have to replace the above command with `source path/to/folder/root-x.xx.xx/bin/thisroot.sh` where `path/to/folder/` is the path to the folder in which you installed ROOT previously.
Now close the file and save it (Ctrl+X and then Ctrl+Y or Ctrl+S if you have an italian language shell). Close also the shell an reopen a new one and your installation is 100% completed. 

### Other installation methods (not recommended)

There are other ways to install ROOT via package managers, however, since these packages are not maintained by the ROOT team, but by helpful members of the community, there may be issues in the installation regarding different versions of the operating system you use or many other. Therefore, consider this kind of installation as a last-chance installation method and use it only in case in which you failed with both the previous installations with binary and source and you plan to host a temporary root installation until you will be able to install a good one.

The first method is with [Conda](https://www.anaconda.com/products/individual) package manager. You can get it from the previos link and type this commands in order to install ROOT:
```shell
conda config --set channel_priority strict
conda create -c conda-forge --name environment root
conda activate environment
```
and the installation is done.
> Setting channel_priority to strict is required to avoid conflicts on some platforms
> Further instructions on how to use this package can be found [here](https://iscinumpy.gitlab.io/post/root-conda/).

The second method is with the *snap* package manager (which can be installed from [here](https://snapcraft.io/docs/installing-snap-on-ubuntu)):
```shell
sudo snap install root-framework
snap run root-framework
```
and the installation is completed.

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
If a new window is opened then you have 100% completed the ROOT installation.
> Please note that `root [0]` indicates the line number of the ROOT command prompt in which you are writing the current ROOT bash command, therefore, from the previous line, you have to copy only `new TBrowser()` in your shell.

> Note also that if you are running `new TBrowser()` command on Windows subsistem for Linux and it gives you and error you probably missed the final part of the [Windows subsistem for Linux ROOT installation[(https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Windows.md).
