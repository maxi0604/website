+++
title = 'Install AMD (previously Xilinx) Vivado on Arch Linux'
date = 2024-05-16T14:52:51+02:00
draft = false
+++

> TLDR: `paru -S ncurses5-compat-libs` or the installer will hang.
> Also, read the wonderful [Arch Wiki page](https://wiki.archlinux.org/title/Xilinx_Vivado) to which I contributed this information

When you want to design hardware, you'll likely start by developing for an FPGA. You have two main options for this, namely AMD's Vivado or Intel's (previously Altera's) Quartus Prime. This article documents how I run the former on [Arch Linux](https://archlinux.org).

# Installation
To install Vivado 2023.2 on Arch Linux (without the AUR package, since I've been told it doesn't work), one can:
+ Install [this AUR package](https://aur.archlinux.org/packages/ncurses5-compat-libs) using an AUR helper like [paru](https://github.com/Morganamilo/paru). This is important, as the installer hangs at "Generating installed devices list" otherwise.
+ Download the `AMD Unified Installer for FPGAs & Adaptive SoCs 2023.2: Linux Self Extracting Web Installer` from [this link](https://www.xilinx.com/support/download.html)
+ Fill out the form
+ Choose `/home/<my username>/vivado` as an install path (using a hidden path or `/opt` may be desirable)
+ Run the installer

# Changing/Interrupting Installation
When the installation has been interrupted or you want to install more features afterwards, it's important to run `<install location>/.xinstall/Vivado_<version>/xsetup` instead of the installer you downloaded, as it will recognize the already present (maybe partial) installation and not redownload or reinstall all the files.
