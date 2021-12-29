# Useful Guides

## Table of contents
- [Introduction](#introduction)
- [Structure of the repository](#structure-of-the-repository)
- [Credits](#credits)

## Introduction

In this repository you can find a set of useful guides I wrote for beginners. Before start talking you about the repository I want to inform you about some things:
- Please, contact me if you find a typo, an error or something that seems not so clear in the repository, I will modify it as soon as possible. In this case please write me to my institutional mail: gianluca.bianco4@unibo.it.
- Contact me if you need help understanding something, especially if you are a student. In this case I would be very happy to help you.
- In case in which material is taken and modified from other people / courses they will be mentioned in the [Credits](#credits) section.

## Structure of the repository

Repository diagram structure:
```
useful-guides/
├── ROOT/
│   ├── Installation/
│   │   ├── MacOS.md
│   │   ├── Ubuntu.md
│   │   ├── Uninstall.md
│   │   ├── Windows.md
│   ├── Quick tips/
│   │   ├── Compilation and Running.md
│   │   ├── ROOT on VS Code.md
│── README.md
│── CITATION.cff
│── License
```

Here the list of the current folder of the repository:
- [**ROOT**](https://github.com/JustWhit3/useful-guides/tree/main/ROOT): which contains [ROOT](https://github.com/root-project/root) framework guides, and in particular the following sub-folders:
  * 💿 [**Installation**](https://github.com/JustWhit3/useful-guides/tree/main/ROOT/Installation): which contains installation guides I wrote for students of the bachelor degree in physics at University of Bologna. These guides have been written by considering all the common issues students had during the framework installation procedure. They are available for the following operating systems: [MacOS](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/MacOS.md), [Windows](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Windows.md) and [Ubuntu](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Ubuntu.md). An extra document for ROOT [uninstallation](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Installation/Uninstall.md) is also provided.
       > Note: in case you have previously installed an old or not working ROOT version, I warmly suggest you to first uninstall it before proceeding with a new one.

       > Hint: if you have to download an Ubuntu release (for example for Windows) it is recommended to download an [LTS](https://ubuntu.com/blog/what-is-an-ubuntu-lts-release) version of it.
  * 💥 [**Quick tips**](https://github.com/JustWhit3/useful-guides/tree/main/ROOT/Quick%20tips): which contains tips for ROOT beginners. You can find something related to the following topics:
    - [Compiling and Running](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Quick%20tips/Compilation%20and%20Running.md): which contains for example some tips about how to compile ROOT macros which depend on other user classes or how to run ROOT macros without entering the ROOT command prompt every time.
    - [ROOT on VS Code](https://github.com/JustWhit3/useful-guides/blob/main/ROOT/Quick%20tips/ROOT%20on%20VS%20Code.md) (work in progress): which explains how to set ROOT framework on VS Code.

## Credits

Some of the material of this repository has been taken and modified / mixed from the following people / courses:
- Slides of Prof. [Silvia Arcelli](https://www.unibo.it/sitoweb/silvia.arcelli) from the course "[Laboratorio di Elettromagnetismo e Ottica [Modulo 3]](https://www.unibo.it/it/didattica/insegnamenti/insegnamento/2021/434322)" at University of Bologna, for the ROOT installation on Ubuntu, MacOS and Windows.
- CERN ROOT [installing page](https://root.cern/install/) for the ROOT installation from alternative ways.

