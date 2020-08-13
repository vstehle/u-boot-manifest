.. SPDX-License-Identifier: GPL-2.0+
.. Copyright (C) Arm Limited, 2020

U-Boot Image Builder Manifest
=============================

Manifest of git repositories to be used with the U-Boot+TFA build scripts.
It uses the git 'repo' tool to clone a copy of each project and a Makefile
from the `u-boot-tfa-build` project to build for various Arm targets.
See the `https://github.com/glikely/u-boot-tfa-build` repo for more details.

Using this tool
---------------
This tool uses the git 'repo' tool.
Install repo first

To initialize the build environment, create a new working directory
and run the repo init command::

  $ mkdir firmware-working
  $ cd firmware-working
  $ repo init -u https://github.com/glikely/u-boot-manifest
  $ repo sync

This will clone all of the required git trees and link the Makefile
into the root directory. To build the firmware, simply type::

  $ make <target_name>_defconfig
  $ make

Where <target_name> is a U-Boot defconfig that can be found in the
u-boot/configs directory.

