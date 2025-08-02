---
title: Using VRSlib
nav_order: 1
parent: Tutorials
layout: default
---

# Using VRSLib

> Note:
>  Make sure you have ran `sudo make install` in the build directory of VRS
>  before doing this.

VRSLib has many dependencies and it can be quite hard to link the
dependencies in the right order. Because its CMake library file is not very
polished (and there was only one file that needed it), G++ was used instead.
The command is:

```bash
g++ file_namename.cpp -o executable_name \
    -L/usr/local/lib \
    -I/usr/local/include \
    -lvrs_utils \
    -lvrs_utils_converters \
    -lvrs_utils_cli \
    -lvrs_helpers \
    -lvrslib \
    -lvrs_os \
    -lvrs_logging \
    -lvrs_utils_xxhash \
    -llz4 \
    -lzstd \
    -lboost_filesystem \
    -lboost_system \
    -lxxhash \
    -lfmt \
    -lpthread
```
