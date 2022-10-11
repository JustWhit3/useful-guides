# ROOT framework installation on Ubuntu operating system

## Table of contents
- [Shell script installer](#shell-script-installer)
- [Installation](#installation)
  * [Proceed via binary distribution (warmly recommended)](#proceed-via-binary-distribution-warmly-recommended)
  * [Proceed via source code](#proceed-via-source-code)
  * [Other installation methods (not recommended)](#other-installation-methods-not-recommended)
- [Installation check](#installation-check)

## Shell script installer

Before talking about the real guide, I want to inform you that I developed a shell script that automatically install the ROOT framework in your computer, by only entering just a command in the terminal command prompt! This script is available for Ubuntu, Windows and MacOS operating systems and fully supports many of the common installation methods (binary, source, package manager etc...). You can find more information and instructions about how to use it [here](https://github.com/JustWhit3/root-framework-installer). If you prefer to install the framework manually and to check step-by-step passages during the installation (recommended), therefore you can continue with the following guide.

## Installation

In this guide you can find some common ways of installing the C++ ROOT framework in your Ubuntu operating system. There are many ways to proceed, however I **warmly** suggest you yo install Ubuntu via binary distribution, since this is the simplest and most efficient method to get the framework working in your machine. Alternatively, and in case you cannot any way solve issues with binary installation, you have first to [uninstall](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Uninstall.md) the software and then to proceed with other installation possibilities: I suggest you first to try to build ROOT from source code and if also this doesn't work (very unlikely) you can try alternative ways, but please try to avoid them if possible.

Before choosing the installation method you have firstly to update your operating system, in order to be sure that all programs are correctly updated and set for the procedure. Open a fresh shell and enter this two commands:

```shell
sudo apt upgrade
sudo apt update
```

Now you have to install all the prerequisite packages. Mandatory are (type the following command on the shell):

```shell
sudo apt install git dpkg-dev cmake g++ gcc binutils libx11-dev libxpm-dev libxft-dev libxext-dev
```

Other not mandatory, but recommended are:

```shell
sudo apt install gfortran libssl-dev libpcre3-dev xlibmesa-glu-dev libftgl-dev libmysqlclient-dev libfftw3-dev libcfitsio-dev graphviz-dev libavahi-compat-libdnssd-dev libldap2-dev python2-dev libxml2-dev libkrb5-dev libgsl0-dev
```
> :warning: Please note that it is warmly suggested to install also the prerequisite packages in order to avoid encountering future ROOT errors about libraries paths not found.

After the system has been updated, decide in which folder you want to install ROOT and enter it through the shell.

> :warning: If you want to install it in the `$HOME` directory you don't have to do anything, just open a new shell and continue with the following steps. Instead, if you want to install it for example in a directory named `dir`, which is located in `path/to/directory` path, you have to type `cd path/to/directory/dir` first, and then proceed with the guide. However, I recommend you to install it in the `$HOME` directory.

### Proceed via binary distribution (warmly recommended)

Once you have completed the prerequisites you can proceed with the real installation. As previously mentioned, this is (in my opinion)  the most efficient and intuitive way to install the ROOT framework. First of all you have to download the release from this [link](https://root.cern/install/all_releases/); click on the **latest** release button and choose the binary distribution corresponding to your operating system version.

> :warning: To know the operating system version of your computer simply type this command on the shell: `lsb_release -a`.
 
Once the zipped folder is downloaded you have to move it from the download section to the $HOME (or to another directory if you planned to install it there):

```shell
mv $HOME/Downloads/root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar.gz $HOME/.
```

where `Downloads` can be replaced with the name of the download folder of your computer (in italian usually is `Scaricati`).

> :warning: Pay attention that `root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar.gz` have to be replaced with the name of the version you are installing. For example if you are installing the Ubuntu 20 binary it would be something like `root_v6.24.06.Linux-ubuntu20-x86_64-gcc9.3.tar.gz`. You can easily see it at the moment of the download of the release.

> :warning: **For Windows users**: if you are installing ROOT on an Ubuntu shell of Windows you can type this command on the Ubuntu shell `explorer.exe .` (note the final dot) in order to know in which position of the Windows system is stored the Ubuntu directory. Then you can manually copy the downloaded ROOT folder from Windows to the Ubuntu previously mentioned folder.

Now unzip it by typing these two commands:

```shell
gunzip root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar.gz
tar -xvf root_vx.xx.xx.Linux-ubuntu18-x86_64-gccx.x.tar
```

> :warning: Remember again to replace the `x` with the version numbers.

Ok, now if you enter:
```shell
ls
```
you can see that, among all the folders of your system there is also a new one called `root`. 

To complete the installation you have to set up the ROOT environment. In order to avoid repeating this latter command every time you enter the shell, you can do the following passages. 

Go in the `$HOME` directory by entering:

```shell
cd $HOME
```

and open the .bashrc file:

```shell
nano .bashrc
```

> :warning: *nano* is the name of the default editor of Ubuntu but you can also use others like *gedit*, *emacs*, *code* or whatever you prefer.

go at the end of the file and add this line:

```shell
source root/bin/thisroot.sh
```

> :warning: If you arein the `$HOME` directory you are ok, but if you planned to install ROOT in a different directory from `$HOME` you have to replace the above command with `source path/to/folder/root/bin/thisroot.sh` where `path/to/folder/` is the path to the folder in which you unzipped ROOT previously.

Now close the file and save it (Ctrl+X and then Ctrl+Y or Ctrl+S if you have an italian language shell). 

Close also the shell an reopen a new one and your installation is 100% completed. 

### Proceed via source code

Another way to install ROOT is via source code. This is another good way to install the framework, but since it is more complicated with respect to previous one, I suggest you to try this only in case the other one fails.

First of all you have to download the release from this [link](https://root.cern/install/all_releases/). Click on the latest release button and choose the source distribution link for download.

Once the zipped folder is downloaded you have to move it from the download section to the home (or to another directory if you planned to install it there):

```shell
mv $HOME/Downloads/root_vx.xx.xx.source.tar.gz $HOME/.
```

where `Downloads` can be replaced with the name of the download folder of your computer (in italian usually is `Scaricati`).

> :warning: Pay attention that `root_vx.xx.xx.source.tar.gz` have to be replaced with the name of the version you are installing. For example if you are installing the latest version it would be something like `root_v6.24.06.source.tar.gz`.

> :warning: **For Windows users**: if you are installing ROOT in an Ubuntu shell of Windows you can type this command on the Ubuntu shell `explorer.exe .` (note the final dot) in order to know in which position of the Windows system is stored the Ubuntu folder. Then you can copy manually the downloaded ROOT folder from Windows to the Ubuntu previously mentioned folder.

Now unzip it by typing these two commands:

```shell
gunzip root_vx.xx.xx.source.tar.gz
tar -xvf root_vx.xx.xx.source.tar.tar
```

> :warning: Remember again to replace the `x` with the version numbers.

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

b) enter it:

```shell
cd root-build
```

c) configure it:

```shell
cmake $HOME/root-x.xx.xx
```

> :warning: If you planned to install ROOT in a different directory from `$HOME`, you have to replace the above command with `cmake path/to/folder/root-x.xx.xx` where `path/to/folder/` is the path to the folder in which you downloaded ROOT previously.

d) and compile it (this will take a while):
```shell
cmake --build .
```
> :warning: Sometimes it may happens that Cmake compilation crashes. This could be due to an error you did in one of the previous passages, or it may be related to the fact that you forgot updating the system before. However there is also the possibility that, since this compilation command takes several minutes (and maybe hours) it crashes for other motivations regarding your machine. In this latter case you can simply try to run the command again without doing anything else more.

Finally, to complete the installation you have to set up the ROOT environment in order to avoid repeating this latter command every time you enter the shell. You can do the following passages:

Go in the `$HOME` directory:
```shell
cd $HOME
```
and open the .bashrc file:
```shell
nano .bashrc
```
> :warning: *nano* is the name of the default editor of Ubuntu. You can also use better editors like *gedit*, *emacs*, *code* or whatever you prefer.

Go at the end of the file and add this line:
```shell
source root-build/bin/thisroot.sh
```
> :warning: If you planned to install ROOT in a different directory from `$HOME`, you have to replace the above command with `source path/to/folder/root-build/bin/thisroot.sh` where `path/to/folder/` is the path to the folder in which you unzipped ROOT previously.

Now close the file and save it (Ctrl+X and then Ctrl+Y or Ctrl+S if you have an italian language shell). 

Close also the shell an reopen a new one and your installation is 100% completed. 

### Other installation methods (not recommended)

There are other ways to install ROOT via package managers, however, since these packages are not maintained by the ROOT team, but by helpful members of the community, there may be issues in the installation regarding different versions of the operating system you use or other problems. Therefore, consider this kind of installation as a last-chance method and use it only in case in which you failed with both the previous installations with binary and source and in case you are planning to host a temporary root installation in your computer until you will be able to get a good one.

The first method is with [Conda](https://www.anaconda.com/products/individual) package manager. You can get it from the previous link and type this commands in order to install ROOT:

```shell
conda config --set channel_priority strict
conda create -c conda-forge --name environment root
conda activate environment
```

and the installation is done.

> :warning: Setting channel_priority to strict is required to avoid conflicts on some platforms.

> :warning: Further instructions on how to use this package can be found [here](https://iscinumpy.gitlab.io/post/root-conda/).

The second method is with [snap](https://snapcraft.io/docs/installing-snap-on-ubuntu):
```shell
sudo snap install root-framework
snap run root-framework
```
and the installation is completed.

## Installation check

Once tou have installed root, you need to check if all the features have been correctly installed. Open a new shell and type:

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

now you are able to run and compile macros. Then, type this command to see if also graphical tools work:

```shell
root [0] new TBrowser()
```

If a new window is opened then you have 100% completed the ROOT installation.

> :warning: Please note that `root [0]` indicates the line number of the ROOT command prompt in which you are writing the current ROOT bash command, therefore, from the previous line, you have to copy only `new TBrowser()` in your shell.

> :warning: Note also that if you are running `new TBrowser()` command on Windows subsistem for Linux and it gives you and error you probably missed the final part of the [Windows subsistem for Linux ROOT installation](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Windows.md).

> :warning: In some very rare cases may happens also that some libraries are not recognized when trying to load or run a macro. You may try to solve this issue installing the package dependencies as root user. See this [video guide](https://www.youtube.com/watch?v=nkKxNBuqsB0&t=186s).
