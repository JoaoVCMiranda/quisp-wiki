# [Work in Progress] step to set up a Windows development environment for QuISP 

## [work in progress] script
```cmd
IF NOT EXIST "omnet5.zip" (curl -o omnet5.zip -LJ --url "https://github.com/omnetpp/omnetpp/releases/download/omnetpp-5.6.2/omnetpp-5.6.2-src-windows.zip")
IF NOT EXIST "omnet6.zip" (curl -o omnet6.zip -LJ --url "https://github.com/omnetpp/omnetpp/releases/download/omnetpp-6.0pre11/omnetpp-6.0pre11-src-windows.zip")
IF NOT EXIST "omnetpp-5.6.2" (
  IF NOT EXIST "omnet5" (call powershell -Command "Expand-Archive -Force omnet5.zip")
  move omnet5\omnetpp-5.6.2 .
  rmdir omnet5
)
IF NOT EXIST "omnetpp-6.0pre11" (
  IF NOT EXIST "omnet6" (call powershell -Command "Expand-Archive -Force omnet6.zip")
  move omnet6\omnetpp-6.0pre11 .
  rmdir omnet6
)
IF EXIST "omnetpp-6.0pre11" (
  del omnetpp-5.6.2\mingwenv.cmd
  rmdir /s /q omnetpp-5.6.2\tools
  move omnetpp-6.0pre11\mingwenv.cmd omnetpp-5.6.2\mingwenv.cmd
  move omnetpp-6.0pre11\tools omnetpp-5.6.2\
  rmdir /s /q omnetpp-6.0pre11
)
 
pause
call "omnetpp-5.6.2\mingwenv.cmd"
```

## download OMNeT++5 and OMNeT++6 preview

choose windows and download it and unzip it
* [OMNeT++5](https://omnetpp.org/download/)
* [OMNeT++6 preview](https://omnetpp.org/download/preview)

I tried with OMNeT++ 6.0 preview11 and OMNeT++ 5.6.2

## move OMNeT++6's `tools` into OMNeT++5
`tools` directory contains msys2 and the toolchain. 
1. remove the OMNeT++5's `tools` directory and `mingwenv.cmd` 
1. move OMNeT++6's `tools` directory and `mingwenv.cmd` to OMNeT++5's directory.

## set up msys2
1. just click `mingwenv.cmd` in the OMNeT++5 directory and follow the prompt says.
1. when finish setting up, you can see the msys2 terminal. 
1. you can see `clang-format --version` shows that you have a newer version of clang: 11.0.0

## build OMNeT++5
1. run `./configure`. you may need to disable OSG by editing the `configure.user` file.
1. run `make -j`. it will take a long time.
1. now you built OMNeT++5 with a new msys2 environment!

## build QuISP
install eigen and set `PKG_CONFIG_PATH` and tweak `eigen3.pc`

## build google test
you need to run `cmake .. -G "Unix Makefiles" in the `googletest/build` dir. later I'll send PR to fix this

# note
for development QuISP with windows. we need [clang](https://clang.llvm.org/) 11 or later and its toolchain (clang-format and clang-tidy), 
but OMNeT++5 contains an old version of msys2 and the toolchain.
[msys2](https://www.msys2.org/) provides [pacman](https://wiki.archlinux.org/title/pacman) the package manager, 
but we cannot update the toolchain (includes clang) 
because of [the pacman's drastic change](https://www.msys2.org/news/#2020-12-26-zstd-exemption-for-core-packages-removed).

I tried to upgrade the pacman and msys2-runtime but it's pretty difficult to do it.
so I gave up and found another way to update msys2 and the toolchain.
