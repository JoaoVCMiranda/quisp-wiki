# INSTALLATION

This document walks you through downloading QuISP, then installing and
building the related software.  Importing QuISP itself into OMNeT++
and building and executing it can be done in two distinct ways,
documented separately (scroll down to the end of this document).

You should assume that reading the instructions, installing from
source, and getting QuISP to run will take you two to four hours the
first time.

## Notation

These installation instructions are interlaced with one example of running the
installation on Linux. Every shell sample will look like this:

```sh
/the/current/directory λ echo HELLO WORLD
HELLO WORLD
```

You type the part after the lambda character (beginning with "echo" in
the example above).

## QUISP

You can get the source for quisp and put it pretty much anywhere you want.

```sh
/home λ mkdir projects && cd projects
/home/projects λ git clone https://github.com/sfc-aqua/quisp.git
Cloning into 'quisp'...
remote: Counting objects: 1222, done.
remote: Compressing objects: 100% (1006/1006), done.
remote: Total 1222 (delta 895), reused 287 (delta 176)
Receiving objects: 100% (1222/1222), 3.79 MiB | 1.61 MiB/s, done.
Resolving deltas: 100% (895/895), done.
```

At this point your file system looks like this.

```
home/
└── projects/
    └── quisp/
        └── .git/
```

## OMNeT++

Get the release of OMNeT++ 5.6.2 from [their website](https://omnetpp.org/) and uncompress it in the folder of your
choice. To remain general, this example uncompresses it in a local libraries folder, far from the quisp project and from standard installation folders.

```
home/
├── projects/
│   └── quisp/
│       └── .git/
└── downloads/
    └── omnetpp-5.6.2-src-linux.tgz
```

```sh
/home λ mkdir -p .local/lib && cd .local/lib
/home/.local/lib λ tar -xzf /home/downloads/omnetpp-5.6.2-src-linux.tgz
```

At this point there is no `omnetpp` binary because you still need to build from
the source release.

```
home/
├── projects/
│   └── quisp/
│       └── .git/
├── downloads/
│   └── omnetpp-5.6.2-src-linux.tgz
└── .local/
    └── lib/
        └── omnetpp-5.6.2/
            ├── configure*
            ├── INSTALL
            ├── Makefile
            ├── README
            ├── setenv*
            ├── bin/
            └── doc/
```

### Building OmNET++

Building information is available in the `doc/InstallGuide.pdf` file of their
source release. Here is a quick version of it on linux.

Compiling OMNeT++ takes time. Be patient.

```sh
/home/.local/lib/omnetpp-5.6.2 λ source setenv
/home/.local/lib/omnetpp-5.6.2 λ ./configure
checking build system type... x86_64-unknown-linux-gnu
checking host system type... x86_64-unknown-linux-gnu
configure: -----------------------------------------------
configure: reading configure.user for your custom settings
configure: -----------------------------------------------
checking for clang... no
checking for icc... no
checking for gcc... gcc

...

Your PATH contains /tmp/tmp.home/home/.local/lib/omnetpp-5.6.2/bin. Good!

/home/.local/lib/omnetpp-5.6.2 λ make -j9
make -s MODE=release
***** Configuration: MODE=release, TOOLCHAIN_NAME=gcc, LIB_SUFFIX=.so ****
===== Checking environment =====

...

Creating executable: out/gcc-debug//osg-satellites_dbg

Now you can type "omnetpp" to start the IDE
```

## Help Me!!!

If you are having trouble with the install, you can peruse the [FAQ](/sfc-aqua/quisp/wiki/FAQ).

## Next Step: QuISP!

There are two main ways of working with QUISP. You can either use the
Eclipse-based graphical interface of OMNeT++, for which you will find
instructions in [Setup OMNeT++ IDE](/sfc-aqua/quisp/wiki/Setup-OMNeT-IDE),
or you can use the `Makefile` and GNU make, by looking at instructions
in [Setup GNU Make](/sfc-aqua/quisp/wiki/Setup-GNU-Make). Some operations are
implemented in the Makefile and not explained for the graphical user
interface.