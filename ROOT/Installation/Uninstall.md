# Uninstall ROOT framework

PLease read the following guide carefully in order to uninstall the framework correctly.

To uninstall the ROOT framework from your computer you have first to open an Ubuntu / MacOS shell and find the path in which the ROOT folder is located (without entering it). If this path corresponds to the `home` folder you don't have to do anything, but if it is different you have to reach it with:
```shell
cd /path/to/root/folder
```
where `/path/to/root/folder` is the path to reach the root installation folder. Now type this command:
```shell
ls
```
and you may see all the ROOT installation folders named as `root` or `root-x.xx.xx` (where `x.xx.xx` is the ROOT version name, for example 6.20.02) and `root-build` or similar depending on the case in which you installed it from binary, from source or from other Ubuntu / MacOS package managers.
> If you have a folder named as `root` be very sure that it is the right one and not a folder containing root-user information of your operating system.
Now you have to delete all them by typing:
```shell
rm -rf root-folder-name
```
where `root-folder-name` is the name of the folder containing the ROOT code.
> If you have to delete more than one folder, repeat the above command for each folder name or put all the folder names in one line separated by a space.
Now, if you are not already in the `home` directory reach it by typing
```shell
cd
```
and opend the .bashrc file with this command:
```shell
editor .bashrc
```
where editor is the editor name you use to open files (ex: *nano*, *gedit*, *emacs*, *code* etc... Default is *nano*).
