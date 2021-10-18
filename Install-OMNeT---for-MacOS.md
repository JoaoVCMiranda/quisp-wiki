<!-- ## Install GNU Make
run `$ brew install make`. then you can check `$ gmake --version`. 
if you don't have `brew` command, install [HomeBrew](https://brew.sh/) first.

In MacOS, `make` is provided as `/usr/bin/make`, but its version is 3.81. 
This version cannot build OMNeT++ properly. HomeBrew installs GNU Make 4 as `gmake`.
when you run `source setenv`, your system aliases `make` to `gmake`.
-->

## Download OMNeT++5
1. get the latest release (5.7 for now) of OMNeT++ for MacOS from their website [https://omnetpp.org/download/](https://omnetpp.org/download/). <br/>click "MAC OS" tab, and then click the green "DONWLOAD" button. <img src="https://i.imgur.com/ZC7bwRo.png"/>

2. uncompress it. you can just click "omnetpp-5.x-macos-x86_64.tgz" in "Finder" to uncompress. ![](https://i.imgur.com/QBESAay.png)
3. put it where you want

## Build OMNeT++5
1. go to `omnetpp-5.x`.
2. run `source setenv` to reflect environment variables.
```sh
$ source setenv
Environment for 'omnetpp-5.7' in directory '/Users/zigen/src/omnetpp-5.7' is ready.
```
3. run `./configure`
```sh
./configure
configure: Environment variables (e.g. PATH) are correctly set.
configure: reading configure.user for your custom settings
checking build system type... x86_64-apple-darwin20.6.0
checking host system type... x86_64-apple-darwin20.6.0
checking for clang... clang
...
checking for LibXML XML parser with CFLAGS="  " LIBS="-lxml2"... yes
configure: Using LibXML for XML parsing
checking for zlib with CFLAGS="  " LIBS="-lz"... yes
checking for Akaroa with CFLAGS="  -I/usr/local/akaroa/include" LIBS="-L/usr/local/akaroa/lib -lakaroa -lfl"... no
configure: WARNING: Optional package Akaroa not found
configure: creating ./config.status
config.status: creating Makefile.inc
config.status: creating src/qtenv/qtenv.pri

WARNING: The configuration script could not detect the following packages:

    MPI (optional)  Akaroa (optional)

Scroll up to see the warning messages (use shift+PgUp), and search config.log
for more details. While you can use OMNeT++ in the current configuration,
be aware that some functionality may be unavailable or incomplete.
```
you might need to permit the execution for toolchain under `omnetpp-5.x/tools/macosx/bin`. see [Open a Mac app from an unidentified developer](https://support.apple.com/guide/mac-help/open-a-mac-app-from-an-unidentified-developer-mh40616/mac)

4. run `make` 
```sh
$ make

Building release and debug mode executables. Type 'make help' for further options.

***** Configuration: MODE=release, TOOLCHAIN_NAME=clang, SHARED_LIBS=yes, LIB_SUFFIX=.dylib ****
===== Checking environment =====
===== Compiling utils ====
===== Compiling common ====
YACC: expression.y
expression.y: warning: 46 shift/reduce conflicts [-Wconflicts-sr]
YACC: matchexpression.y
lcgrandom.cc
filereader.cc
linetokenizer.cc
...
```
## Start OMNeT++5 IDE 
1. run `omnetpp`
then you can see the eclipse based OMNeT++ IDE