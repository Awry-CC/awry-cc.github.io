---
title: Linux
permalink: /docs/install-linux/
---

<div class="alert alert-danger" role="alert">
  Review all commands. Copy and pasting commands is discouraged.
</div>

Awry is built on linux and uses GNU autotools for its build system. An example build workflow is defined in the <a href="https://github.com/Awry-CC/awry/blob/master/.github/workflows/Ubuntu.yml" target="_blank">Github Actions</a> for Ubuntu.

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

make sharedlib will compile the Awry library to `lib/libawry.X.X.X.so`.

```bash
make sharedlib
```

### 4. Install the library

Installation of the shared library to `/usr/local/lib` and the headers to `/usr/local/include/awry` requires **sudo** permissions.

```bash
sudo make install
```

### 5. Build and run the test suite


```bash
make tests ; ./bin/testsuite
```

### 6. Alternative

The default make command will run all of the above commands, but requires **sudo** permissions to run the install. Run the default make command under **sudo** only after reviewing the Makefile output from step 2.

```bash
sudo make
```