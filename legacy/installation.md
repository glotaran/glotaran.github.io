---
layout: default
permalink: /legacy/installation
title: installation
---
[← Back to start](/legacy)

## Installation <!-- omit in toc -->

- [Requirements](#requirements)
- [Step 1: Installation](#step-1-installation)
  - [Installation notes](#installation-notes)
    - [Windows installation](#windows-installation)
    - [Linux installation](#linux-installation)
    - [Mac OS X installation](#mac-os-x-installation)
- [Step 2: Configuration and set up](#step-2-configuration-and-set-up)
  - [Step 2a: Installing the R package `TIMP`](#step-2a-installing-the-r-package-timp)
  - [Step 2b: Installing the R package `Rserve`](#step-2b-installing-the-r-package-rserve)
  - [Step 2c: Starting up `Rserve`](#step-2c-starting-up-rserve)
    - [Windows set-up](#windows-set-up)
      - [Method 1: Starting `Rserve` from the `R` GUI](#method-1-starting-rserve-from-the-r-gui)
      - [Method 2: Starting Rserve from the command line](#method-2-starting-rserve-from-the-command-line)
    - [Linux and Max OS X set-up](#linux-and-max-os-x-set-up)
- [Step 3: Starting Glotaran](#step-3-starting-glotaran)
- [Step 4: Updating](#step-4-updating)

### Requirements

Before installing Glotaran, please check to see if your system meets the
specified [requirements](./requirements.html "system requirements for glotaran-legacy").

_Please note that R is only supported up to version R 4.0.5, R 4.1.x is **not yet supported**._

### Step 1: Installation

Glotaran can be downloaded from [github](https://github.com/glotaran/glotaran-legacy/releases/ "glotaran/glotaran-legacy/releases").
Note that there are different installers for each operating system (Windows, Mac OS X, Linux). Alternatively, a system independent zip distribution is also
available which runs on any platform that has [Java SE 8](http://www.java.com/ "Java SE 8 or Java 1.8") installed.

#### Installation notes

##### Windows installation

Under newer versions of Windows it might not always be possible to install
Glotaran in the \"Programs\" or \"Program Files\" folder without having
elevated administrator rights. However, Glotaran can also safely be
installed in for instance the Documents folder. Alternatively you can
safely run the System Independent Zip distribution directly from your
Downloads or Documents folder.

##### Linux installation

It might be necessary to make the installer executable. This can be done
by issues the command `chmod +x <file_name_of_the_installer>`
from the command line, or \- depending on the Desktop Environment \- right
clicking the installer and selecting \'executable\' from the properties
dialog.

##### Mac OS X installation

Download the Glotaran Disk Image (dmg) from the website and open it.
Then drag the Glotaran application to your application folder as
normally.

### Step 2: Configuration and set up

To make use of all of the functionality in Glotaran requires a working
installation of R on the machine, with the R packages **`TIMP`** and **`Rserve`** installed.
Otherwise you will not be able to run any new analysis, and only view existing results (such as the included demo project).

If you have not yet installed **`R`**, please refer to the official [R-project
website](http://www.r-project.org/ "The R Project for Statistical Computing") for instructions and install **`R`**, _before proceeding with these notes_.

Once **`R`** has been installed it is important to install the R packages
[**`TIMP`**](https://cran.r-project.org/web/packages/TIMP/ "TIMP on Cran") and [Rserve from CRAN](https://cran.r-project.org/web/packages/Rserve/ "Rserve on CRAN") from CRAN or alternatively [rforge.net](http://www.rforge.net/Rserve/ "Rserve on rforge.net").

If needed, refer to the detailed instructions below.

#### Step 2a: Installing the R package `TIMP`

To install the R package **`TIMP`** , please take the following steps:

1. Start R; either from the command line or start the R GUI
2. Execute the following command: **`install.packages("TIMP")`**

Please note that **`TIMP`** version 1.13 or higher is required for Glotaran
1.5 and higher to run. The above command automatically install the
latest stable version of TIMP.

#### Step 2b: Installing the R package `Rserve`

To install the R package Rserve, please take the following steps:

1. Start R; either from the command line or start the R GUI
2. Execute the following command: **`install.packages("Rserve")`**

#### Step 2c: Starting up `Rserve`

##### Windows set-up

###### Method 1: Starting `Rserve` from the `R` GUI

Other than the method described above, there is another way to start
Rserve - from within the R GUI.

To start Rserve from the R GUI

1. Start the 32-bit version of R (R i386; either from the command line or start the App)
2. Execute the following commands:
   - `library(Rserve)`
   - and one of the following:
     - `Rserve()` (for Windows and Linux/Unix)
     - `Rserve(args='--no-save')`  (for Mac OS X)
     - `Rserve(args='--no-save', debug=TRUE)` (if you run into issues)

###### Method 2: Starting Rserve from the command line

This method may provide more diagnostic information when errors occur.
Find the **R installation location**. Under Windows this is
typically:

- `C:\Program Files\R\R-x.y.z`

Next, locate the **R library folder** where the packages Rserve and TIMP have
been installed in. Under Windows this is typically:

- `C:\Program Files\R\R-x.y.z\library` (if you installed as administrator or with elevated rights)
- `%USERPROFILE%\R\win-library\x.y` (otherwise)

Inside the **R library folder** navigate to the _Rserve_ subfolder.

From the `libs\i386` folder copy the following files from here:

- `Rserve.exe`
- `Rserve_d.exe`

To the i386 folder **_inside_** the bin folder of the **R installation location**, e.g.:

- `C:\Program Files\R\R-x.y.z\bin\i386`

Note: depending on Windows settings you might
not see the .exe extension ([how to change that](https://www.howtogeek.com/205086/beginner-how-to-make-windows-show-file-extensions/ "How to Make Windows Show File Extensions")).

Now run the Rserve executable you just copied to the i386/bin folder from there, to see if it works. If you see a (Windows) Firewall dialog, please unblock the program. Rserve will not work otherwise.

Note you might want to make a shortcut to the Rserve.exe executable out
it on your desktop so you can start it _before_ you start Glotaran.

##### Linux and Max OS X set-up

Linux and Mac OS X require no special steps to setup. Start R (preferably from a terminal) and refer to [method 1](#method-1-starting-rserve-from-the-r-gui)

### Step 3: Starting Glotaran

Now you can start Glotaran from your application menu. Or,
alternatively, you can start Glotaran using the glotaran executable in
the bin sub folder of the Glotaran installation or zip folder.

You can also start Glotaran without starting Rserve first, but then you
will not be able to run any new analysis, and only view existing results
(such as the included demo project).

### Step 4: Updating

This version of Glotaran is no longer actively maintained or updated, hence its rebranding to glotaran-legacy. However, **_if_** a new version is released you can find it on [github](https://github.com/glotaran/glotaran-legacy/releases/ "glotaran/glotaran-legacy/releases").
