# Wingit

The goal or this project is to provide setup scripts and other utilities for after the Windows operating system installation.

## Compatibility Notice

The majority of this project is written in POSIX shell, so it does not natively run on Windows out of the box. Therefore,
there is a requirement for some additional tool to get up and running before the installation itself can be run. One such
tool is **Git for Windows**.

## Installation

First, run the `install.cmd` script in the Windows `cmd.exe`. This script will download various installation packages
one of which will be the above-mentioned **Git for Windows**, which is the only package required to proceed next.

After installation of the **Git for Windows** open its shell, go into directory with the `install` script and run it.

## Environment Variables

There is one file providing env variables to the installation process. This one is the `.env` file, the main so-called configuration file for the whole environment.

This file can have its so-called local version, which is not stored in Git. It uses `.local` suffix, i.e. `.env.local`.

This local version is used mainly for development purposes to override the default env variables.

After the installation process is initiated, this file is read and its env variables are stored in memory.

## Project Structure

The project consists of several main components described bellow:

* `dist`: contains installation and setup scripts of various programs
* `exe`: contains scripts for commands execution, logging and working with env variables among others
* `ins`: contains wrapper scripts for installation and setup scripts
* `lib`: contains wrapper scripts for native shell commands

## SSH Keys

There are two pairs of SSH keys:

* `id_rsa` and `id_rsa.pub`: these keys are used for Git and various services, and they are also password protected
* `id_rsa_git` and `id_rsa_git.pub`: these keys are used only in this project during the installation process to clone Git repositories, and they are not password protected
