succinct
========

This repository contains the implementation of some data structures. I
wrote this code during my Ph.D. for my own experiments, so it is
mostly undocumented and uncommented, and probably generally unclear. 

The "library" is meant to be included as a git submodule in other
projects and then included as a CMake subdirectory. See the project
[semi_index](https://github.com/ot/semi_index) for an example.

How to build the code
---------------------

### Dependencies ###

The following dependencies have to be installed to compile the library.

* CMake >= 2.6, for the build system
* Boost >= 1.42

### Supported systems ###

The code has been developed and tested mainly on Linux, but it has
been tested also on Mac OS X and Windows 7.

The code has been tested only on x86-64. Compiling it on 32bit
architectures would probably require some work.

### Building on Unix ###

The project uses CMake. To build it on Unix systems it should be
sufficient to do the following:

    $ cmake .
    $ make

It is also advised to perform a `make test`, which runs the unit tests.

### Building on Windows ###

On Windows, Boost and zlib are not installed in default locations, so
it is necessary to set some environment variables to allow the build
system to find them.

* For Boost `BOOST_ROOT` must be set to the directory which contains
  the `boost` include directory.
* The directories that contain the Boost must be added to `PATH` so
  that the executables find them

Once the env variables are set, the quickest way to build the code is
by using NMake (instead of the default Visual Studio). Run the
following commands in a Visual Studio x64 Command Prompt:

    $ cmake -G "NMake Makefiles" .
    $ nmake
    $ nmake test
