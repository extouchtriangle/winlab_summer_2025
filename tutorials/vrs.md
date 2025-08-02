---
title: Using VRSlib
nav_order: 1
parent: Tutorials
layout: default
---

# Using VRSLib

VRSLib has many dependencies, and it can be quite hard to link them
in the right order during compilation. If you want to compile them without
using CMake (like I did for the one file I wrote using the library),
here is the command to do so:
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

{: .important }
>  Make sure you actually install the library (i. e. `sudo make install`) before running the command above.
