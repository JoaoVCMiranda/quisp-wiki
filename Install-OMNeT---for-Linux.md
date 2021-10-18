# Install OMNeT++5

## Notation

These installation instructions are interlaced with one example of running the
installation on Linux. Every shell sample will look like this:

```sh
/the/current/directory λ echo HELLO WORLD
HELLO WORLD
```

You type the part after the lambda character (beginning with "echo" in
the example above).

## OMNeT++

Get the release of OMNeT++ 5.6.2 or later from [their website](https://omnetpp.org/download/) and uncompress it in the folder of your
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

At this point, there is no `omnetpp` binary because you still need to build from the source release.

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

### Building OMNeT++

Building information is available in the `doc/InstallGuide.pdf` file of their source release. 
Here is a quick version of it on linux.

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

Go to [Setup OMNeT++ IDE](/sfc-aqua/quisp/wiki/Building-QuISP-with-OMNeT-IDE).