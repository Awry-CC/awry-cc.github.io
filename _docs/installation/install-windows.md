---
title: Windows
permalink: /docs/install-windows/
---

<div class="alert alert-danger" role="alert">
  Review all commands. Copy and pasting commands is discouraged.
</div>

Awry will not compile on Windows without additional utilities. The Windows Subsystem for Linux will compile the library for Linux, but Awry will not work with Microsoft Visual C++ in this context. Awry's build system uses MSYS2 for compilation to Windows.

## Install Chocolatey

<a href="https://chocolatey.org/install#individual" target="_blank">Chocolatey<a/> is a package manager for powershell. It provides a package to install MSYS2 on Windows.

Open powershell and run the following command to install Chocolatey:

```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

## Install MSYS2

In the same powershell session, install MSYS2:

```
choco install msys2
```

## Install GNU auto utilities

In the current powershell session, open a bash terminal:

```
bash
```

Then install autoutils, gcc, and other dependencies to build Awry:

```
pacman -Sy autoconf make gcc git automake libtool --noconfirm
```

And clone the repository with git:

```
git clone git@github.com:Awry-CC/awry.git ; cd awry
```

### 1. Generate the configure script

autoconf will generate the configure bash script to find required dependencies.

```bash
autoconf
```

### 2. Generate the makefile

configure will create the final makefile, filling in variables and C flags with what's defined in configure.ac

```bash
./configure
```

### 3. Build the shared library

make sharedlib will compile the Awry library to `lib/libawry.X.X.X.dll`.

```bash
make sharedlib
```

### 4. Install the library

Install the shared library to `C:/Windows/system32` and the headers to `C:/usr/include/awry`.

**NOTE:** You may have to change the includes path to something registered in your `PATH` variable. 

```bash
make install
```

### 5. Build and run the test suite


```bash
make tests ; ./bin/testsuite.exe
```

### 6. Alternative

The default make command will run all of the above commands. Use only after reviewing the generated Makefile.

```bash
make
```