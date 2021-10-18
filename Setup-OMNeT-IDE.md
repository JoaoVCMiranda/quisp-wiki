You are assumed to have just OMNeT++ IDE in your system.

## Set up environment
If you are using Windows, don't forget to click `mingwenv.cmd`.

If you are using Docker, skip this step.

If you are using Linux or MacOSX, you need to run `. setenv` to run the OmNET++ IDE.
```sh
$ source setenv
Environment for 'omnetpp-5.x' in directory '/home/.local/lib/omnetpp-5.x' is ready.
```

## Cloning QuISP
go to where you want to clone QuISP and then clone QuISP from GitHub. 
```sh
$ git clone https://github.com/sfc-aqua/quisp
```
if you are using ssh,
```sh
$ git clone git@github.com:sfc-aqua/quisp
```

## Start OMNeT++ IDE and configure a workspace for QuISP
and then, run `omnetpp` command to start OMNeT++ IDE
```sh
$ omnetpp
Starting the OMNeT++ IDE...
```

This starts the Eclipse Launcher.
When asked to select your workspace, choose the quisp folder (here, `/home/projects/quisp`, not `/home/projects/quisp/quisp`). 

<img src="https://i.imgur.com/xKQGQvr.png"  width="50%" height="50%">

Then, open the Workbench. When warned that your workspace is empty, refuse to install samples and INET framework.

<img src="https://i.imgur.com/LKJJgDX.png" width="50%" height="50%">

Finally, import the QUISP project into your workspace. 
You can use the `File > Import...` menu, then select the `General > Existing Projects into Workspace` wizard.

<img src="https://i.imgur.com/9PzfAyV.png" width="50%" height="50%">

As a root directory of the project, select the quisp folder.
In the list of suggested projects, check the only project that appears then
click `Finish`.

<img src="https://i.imgur.com/V41W3Wp.png" width="50%" height="50%">

When you did this, the GUI created two folders, `.metadata` for the
workspace and `.settings` for the project, that are ignored by the git
repository.

```
quisp/
├── .git/
├── setenv*
├── .metadata/
└── quisp/
     └── .settings/
```

## Configure building

Right click `quisp` in the project explorer and click `Property`.
<img src="https://i.imgur.com/BTE7Bl1.png" width="30%" height="25%">

then in the category `OMNeT++ > Makemake` you should get a warning.
*No makefile has been specified for this project.*
<img src="https://i.imgur.com/cDj1HWg.png" width="50%" height="50%">


Click on the `quisp` folder below the warning, select the `Makemake` box and click `Apply and close`.
<img src="https://i.imgur.com/kCxhNjo.png" width="50%" height="50%">

Now you should be able to build the project with `Ctrl+B` or `Project > Build all`
for example.

## Running interesting simulations

You should now be ready to simulate quantum networks! Go to [running demos](Running-Basic-QuISP-Demos).
