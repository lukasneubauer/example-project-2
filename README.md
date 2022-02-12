# Operating System

The goal or this project is to provide setup scripts and other utilities for after the GNU/Linux operating system installation.

## Installation

The installation process is initiated by running the `install` script.

**NOTE**: To initiate the installation process, root password needs to be entered (a prompt for the root password will appear).

After the installation process is finished, check log files defined by the `OUT_LOG_FILE` and `ERR_LOG_FILE` env variables
(these are `out.log` and `err.log` by default), which are stored in directory defined by `LOGS_DIR` env variable (this is `$HOME_DIR/tmp` by default).

**NOTE**: If there are no errors during the installation, the error log file will not be created.

## Environment Variables

There are several files providing env variables to the installation process. These are:

* `.env`: the main so-called configuration file for the whole environment
* `.env.sudo`: only contains env variable to store root password
* `.env.test`: contains env variables for tests

Each file can have its so-called local version, which is not stored in Git. They use `.local` suffix, i.e. `.env.local`, `.env.sudo.local` and `.env.test.local`.

These local versions are used mainly for development purposes to override the default env variables.

After the installation process is initiated, all these files are read and their env variables are stored in memory.

**NOTE**: The `.env.sudo` file does not actually store root password, but the `.env.sudo.local` does. It is created automatically
after the installation process is initiated and root password is entered into the prompt that appears.

## Project Structure

The project consists of several main components described bellow:

* `deb`: contains wrapper scripts for Debian specific commands
* `dist`: contains installation and setup scripts of various programs
* `exe`: contains scripts for commands execution, logging and working with env variables among others
* `ins`: contains wrapper scripts for installation and setup scripts
* `lib`: contains wrapper scripts for native shell commands

## SSH Keys

There are two pairs of SSH keys:

* `id_rsa` and `id_rsa.pub`: these keys are used for Git and various services, and they are also password protected
* `id_rsa_git` and `id_rsa_git.pub`: these keys are used only in this project during the installation process to clone Git repositories, and they are not password protected

## Standalone Packages

The project also contains several packages which are part of the overall code but are not strictly tied to it and can be also used standalone:

* [disks](disks) - useful information about storage devices
* [g3](g3) - work with multiple remotes inside one single Git repository
* [grub](grub) - useful utility scripts for the Grub bootloader
* [saves](saves) - script for creation of save game backups
* [split](split) - split-out portion of git repository
* [wingc](wingc) - clean up debris files and directories left behind by various systems and applications
* [wingit](wingit) - setup scripts and other utilities for after the Windows operating system installation
