# ROOT framework tips for macros compilation and running

## Table of contents
- [Compile and run a ROOT macro depending on other classes](#compile-and-run-a-ROOT-macro-depending-on-other-classes)
- [Run ROOT commands without entering ROOT shell ever ytime](#run-root-commands-without-entering-root-shell-every-time)

## Compile and run a ROOT macro depending on other classes

Here I want to show you how to compile and run a ROOT macro which depends on other classes.

Supposing you have a class which functionalities are written in *class.h* and *class.cpp* files and you want to include it in a ROOT generation macro called *macro.cpp* which contains ROOT objects and has to be run inside ROOT command prompt shell.
> Hint: it is better to name the *macro.cpp* functions differently from the usual `int main(){}` since you may encounter a `TApplication` error during the macro execution.

In order to correctly compile and run the *macro.cpp* macro you have to follow some steps.

1) Enter the ROOT shell:
```shell
root
```
and manually load the class.
```shell
.L class.cpp+
```
> Add `+` at the end of the macro name in order to force the C++ compilation.

> If you have more than one class you have to do this passage for every single class, starting by the one which less depends on the other until the one which depends more.

Now a file named *class_cpp.so* has been created in the current folder in which you run the previous command, it contains informations for the future macro loading. This passage has to be repeated ever ytime you modify a class. If you write a class and then you have to run only the *macro.cpp* macro, you don't need to repeat the previous command anymore.

2) Open the ROOT macro with you editor, add the include class .h files at the top of the macro and load the class into it by using this two lines of code:
```c++
#include "class.h"
R__LOAD_LIBRARY(class_cpp.so)
```
> Pay attention to the double `_` after `R`. See also that you are using the previously created *_cpp.so* file.

Ok, now the work is completed and, supposing the *macro.cpp* has a function named *macro()*, you can finally run it, once you have entered ROOT shell, with this two commands:
```shell
.L macro.cpp+
macro()
```

Remember also that steps 1. and 2. can be summarized by simply entering the ROOT shell and directly using the `gROOT` pointer:
```shell
gROOT->LoadMacro("class.cpp+")
gROOT->LoadMacro("macro.cpp+")
macro()
```

## Run ROOT commands without entering ROOT shell every time

In case in which you are running multiple ROOT commands and than have to exit ROOT every time to perform other operations, there is a smart solution to automate this process, usefule to run ROOT commands into a .sh shell script without the needing of entering the ROOT shell even once.

First of all, enter the directory in which you plan to create the script that is usually the directory in which you are developing your project:
```shell
cd directory
```
> If it is `$HOME` you can ignore the previous command.

and create the new .sh script:
```shell
touch script.sh
```
Now open it with you editor (default is *nano*) and write this lines of bash code:
```shell
root << EOF
... ROOT commands ...
EOF
```
Looking at it line by line: you are first giving the shell a command for opening ROOT and to tell it to write some bash commands from `EOF` until it will encounter `EOF` again. Between them you can write several ROOT commands (ex: `gROOT->LoadMacro("class.cpp+")`) you have normally wrote entering ROOT everytime and running them into the ROOT shell itself.

Now close and save the script (Ctrl+X and Ctrl+Y or Ctrl+S in case of an italian shell) and make it executable:
```shell
chmod +x script.sh
```
If you now enter in the shell:
```shell
ls
```
you can see that the script name has become green; this means that the script is finalle executable. 

Now, whenever you want to launch the script and make it execute all the commands contained in it, you have to simply enter:
```shell
./script.sh
```
