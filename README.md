# OpenBLAS

## Introduction

This repo contains changes to OpenBLAS to allow it to cross compile for esp32 devices

OpenBLAS is an optimized BLAS library based on GotoBLAS2 1.13 BSD version.

Please read the documentation on the OpenBLAS wiki pages: <http://github.com/xianyi/OpenBLAS/wiki>.

### Dependencies

Building OpenBLAS requires the following to be installed:

* GNU Make
* ESP32 Toolchain <https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#setup-toolchain>

### Cross compile

Set `CC` to point to the cross toolchains, and set `HOSTCC` to your host C compiler.
The target must be specified explicitly when cross compiling.

Examples:

* On an x86 box, compile this library for ESP32:
  ```sh
  make ONLY_CBLAS=1 BINARY=32 CC=$XTENSA_ESP32_GCC HOSTCC=gcc TARGET=ESP32 CORE=ESP32
  ```

### Debug version

A debug version can be built using `make DEBUG=1`.

### Install to a specific directory (optional)

Use `PREFIX=` when invoking `make`, for example

```sh
make install PREFIX=your_installation_directory
```

The default installation directory is `/opt/OpenBLAS`.
