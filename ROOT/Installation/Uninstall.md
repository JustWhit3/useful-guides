# Uninstall ROOT framework

PLease read the following guide *very carefully* in order to uninstall the framework correctly. The procedure is the same whatever is the operating system you used to install ROOT.

To uninstall the framework from your computer you have firstly to open an Ubuntu / MacOS shell and find the path in which the ROOT folder is located (without entering it). 

> If this path corresponds to the `$HOME` directory you don't have to do anything, but if it is different you have to reach it with:
> ```shell
> cd /path/to/root/folder
> ```
> where `/path/to/root/folder` is the path to reach the root installation folder. 
> 
Now type this command:
```shell
ls
```
and you may see all the ROOT installation folders named as `root` or `root-x.xx.xx` (where `x.xx.xx` is the ROOT version name, for example 6.20.02) and `root-build` or similar depending on the case in which you installed it from binary, from source or from other Ubuntu / MacOS package managers.
> If you have a folder named as `root` be sure that it is the right one and not a folder containing root-user information of your operating system.
Now you have to delete all them by typing:
```shell
rm -rf root-folder-name
```
where `root-folder-name` is the name of the folder containing the ROOT code.
> If you have to delete more than one folder, repeat the above command for each folder name or put all the folder names in one line separated by a space.

Now, if you are not already in the `$HOME` directory reach it by typing:
```shell
cd $HOME
```
and opend the .bashrc file with this command:
```shell
nano .bashrc
```
where *nano* is the default editor you can use to open files (if you prefer you can use a better one like *gedit*, *emacs*, *code* etc...), and search for this code line:
```shell
source root/bin/thisroot.sh
```
and remove it.
> Sometimes the path may be different depending on the directory in which you installed ROOT or on the name of the ROOT folder you created when you previously installed the framework, typically it is: `root`, `root-build` or `root-x.xx.xx` (where `x.xx.xx` is the ROOT version name, for example 6.20.02).
