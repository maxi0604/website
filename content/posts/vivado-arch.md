+++
title = 'Install AMD (previously Xilinx) Vivado on Arch Linux'
date = 2024-05-16T14:52:51+02:00
draft = false
+++

> TLDR: `paru -S ncurses5-compat-libs` or the installer will hang.

When you want to design hardware, you'll likely start by developing for an FPGA. You have two main options for this, namely AMD's Vivado or Intel's (previously Altera's) Quartus Prime.

To install Vivado 2023.2 on Arch Linux (without the AUR package, since I've been told it doesn't work), one can:
+ Install [this AUR package](https://aur.archlinux.org/packages/ncurses5-compat-libs) using an AUR helper like [paru](https://github.com/Morganamilo/paru). This is important, as the installer hangs at "Generating installed devices list" otherwise.
+ Download the `AMD Unified Installer for FPGAs & Adaptive SoCs 2023.2: Linux Self Extracting Web Installer` from [this link](https://www.xilinx.com/support/download.html)
+ Fill out the form
+ Choose `/home/<my username>/vivado` as an install path (using a hidden path or `/opt` may be desirable)
+ Run the installer
