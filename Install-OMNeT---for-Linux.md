# Install OMNeT++6

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

Get the release of OMNeT++ 6.0 or later from [their website](https://omnetpp.org/download/) and uncompress it in the folder of your
choice. To remain general, this example uncompresses it in a local libraries folder, far from the quisp project and from standard installation folders.

```
home/
├── projects/
│   └── quisp/
│       └── .git/
└── downloads/
    └── omnetpp-6.1-src-linux.tgz
```

```sh
/home λ mkdir -p .local/lib && cd .local/lib
/home/.local/lib λ tar -xzf /home/downloads/omnetpp-6.1-src-linux.tgz
```

At this point, there is no `omnetpp` binary because you still need to build from the source release.

```
home/
├── projects/
│   └── quisp/
│       └── .git/
├── downloads/
│   └── omnetpp-6.1-src-linux.tgz
└── .local/
    └── lib/
        └── omnetpp-6.1/
            ├── INSTALL.md
            ├── MIGRATION
            ├── Makefile
            ├── Makefile.inc.in
            ├── README
            ├── Version
            ├── WHATSNEW.md
            ├── bin
            ├── configure
            ├── configure.in
            ├── configure.user
            ├── configure.user.dist
            ├── doc
            ├── ide
            ├── images
            ├── include
            ├── install.sh
            ├── lib
            ├── misc
            ├── python
            ├── samples
            ├── setenv
            ├── src
            └── test
```
### Quick setup
Inside the omnetpp-6.1 folder run the command `./install.sh` and it will try to install the required packages in your system. If that doesn't work proceceed to the build from source method.

```bash
/home/.local/lib/omnetpp-6.1/ λ ./install.sh
```

### Build From Source

#### Requirements
> [!TIP]
> These are the common requirements for installing Omnetpp
In order to download and install omnetpp it's recommended to have the following packages

Debian/Ubuntu-based distros
```bash
sudo apt install build-essential\
		 pkg-config \
		 ccache \
		 clang \
		 lld \
		 gdb \
		 bison \
		 flex \
		 perl \
		 python3 \
		 python3-pip \
		 python3-venv \
		 libpython3-dev \
		 libxml2-dev \
		 zlib1g-dev \
		 doxygen \
		 graphviz \
		 xdg-utils \
		 libdw-dev \
		 qtbase5-dev \
		 qtchooser \
		 qt5-qmake \
		 qtbase5-dev-tools \
		 libqt5opengl5-dev \
		 libwebkit2gtk-4.1-0 \
		 libopenscenegraph-dev
```
 
Arch-based distros

```bash
sudo pacman -S --needed base-devel \
			pkg-config \    
			ccache \
			clang \
			lld \
			gdb \
			bison \
			flex \
			perl \
			python \
			python-pip \
			python-virtualenv \
			libxml2 \
			zlib \
			doxygen \
			graphviz \
			xdg-utils \
			libdwarf \
			qt5-base \
			qt5-tools \
			webkit2gtk \
			openscenegraph
```

Fedora/CentOS
```bash
sudo dnf install @development-tools \
                 pkg-config \ 
                 ccache \     
                 clang \     
                 lld \     
                 gdb \     
                 bison \     
                 flex \     
                 perl \     
                 python3 \     
                 python3-pip \     
                 python3-virtualenv \     
                 python3-devel \     
                 libxml2-devel \     
                 zlib-devel \     
                 doxygen \     
                 graphviz \     
                 xdg \-
                 utils \     
                 libdwarf-devel \     
                 qt5-qtbase \-
                 devel \     
                 qtchooser \      
                 webkit2gtk3 \ 
                 OpenSceneGraph
```

##### Python requirements

```
/home/.local/lib/omnetpp-6.1 λ pip install -r python/requirements.txt
```
> [!WARNING]
> If you receive the error: externally-managed-environment
> you might like to use the flag `--break-system-packages`
> Or create a virtual environment

#### Building OMNeT++

Building information is available in the `doc/InstallGuide.pdf` file of their source release. 
Here is a quick version of it on linux.
	
Compiling OMNeT++ takes time. Be patient.

##### Set the environment

```sh
/home/.local/lib/omnetpp-6.1 λ source setenv
```
> [!TIP]
> If you're having trouble mapping the OpenSceneGraph libraries
> Edit the file `configure.user` and set the flag `WITH_OSG` to `no` to disable 3D-view features.

Uncomment the line `#CFLAGS_RELEASE='-O3 -DNDEBUG=1'` to compile it faster.

```configure.user
...
WITH_OSG=no
...
CFLAGS_RELEASE='-O3 -DNDEBUG=1'
...
```

> [!TIP]
> If you get stuck with setting the environment variables for OpenSceneGraph and you're not going to use the 3D-features of the simulador just deactivate it


##### Configure
```sh
/home/.local/lib/omnetpp-6.0 λ ./configure
checking build system type... x86_64-unknown-linux-gnu
checking host system type... x86_64-unknown-linux-gnu
configure: -----------------------------------------------
configure: reading configure.user for your custom settings
configure: -----------------------------------------------
checking for clang... no
checking for icc... no
checking for gcc... gcc
```
This step will show you if you have any missing dependencies


```sh
...

Your PATH contains /tmp/tmp.home/home/.local/lib/omnetpp-6.0/bin. Good!

/home/.local/lib/omnetpp-6.0 λ make -j9
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
