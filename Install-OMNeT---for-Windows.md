## Download OMNeT++5
1. download Windows build from [here](https://omnetpp.org/download/).
2. OMNeT++ will be downloaded as a zip file. Once the download is complete, extract the file, you should see these files in the extracted directory.

![](https://i.imgur.com/oV6n4N4.png)
3. put it where you want.

## Build OMNeT++5
click `mingwenv.cmd`, which will start a console with the MSYS bash shell.
In the shell, type the following commands:

```
$ ./configure
$ make
```
and then, it starts OMNeT++ build.
This might take a while to finish executing.




## Check the build
**To verify** that the installation has been successful, run the following:

```
$ cd samples/aloha
$ ./aloha
```

By default, the samples will run using the graphical Qtenv environment. You should see the following GUI windows.


![](https://i.imgur.com/8PdKzMm.jpg)

**Click OK**



![](https://i.imgur.com/gka2aCx.jpg)


Yay!! your installation was successful!!

**To run** the Omnetpp (OMNeT app), type the command
```
$ omnetpp
```

### Caveat
*Whenever you want to run omnetpp, you will need to run from the mingwenv console*
because this command starts MinGW and adjusts your environment variables.
If you skip this, you can't use OMNeT++ related commands (e.g. `opp_makemake`).



![](https://i.imgur.com/NbQi43n.jpg)

## 2-  Cloning and Building Quisp

To clone and build Quisp, one your terminal (use the mingwenv console to clone the repo) and type the follwoing commands:
```
$ git clone https://github.com/sfc-aqua/quisp.git
```

## 3- Set up OMNeT for the Simulation

*Execute* the command `omnetpp` from mingwenv console. When the dialogue comes up, select your workspace and click *Launch*.

*Warning: Setting workspace as `<Directory where you extracted omnetpp>\omnetpp-5.x.x\quisp` is highly recommended.*



<img src="https://i.imgur.com/xKQGQvr.png"  width="50%" height="50%">



When you see this dialogue, just click *OK*.

<img src="https://i.imgur.com/evHDjQu.png"  width="50%" height="50%">



From File >> Open Projects from File System



![](https://i.imgur.com/F5ikDGK.jpg)

Click *Directroy* and find the location where Quisp was cloned (usually it will be in the omnet directroy). Select the `quisp` directory under the cloned `quisp`. So it should be `<Directory where you cloned quisp>\quisp\quisp`



![](https://i.imgur.com/XMVnRse.jpg)

Select `quisp` and click *Finish*



<img src="https://i.imgur.com/G7IV5B9.png"  width="50%" height="50%">

That will make *quisp* and *quisp* appear in your **Project Explorer**

Select quisp, right-click on it and choose *properties*.



![](https://i.imgur.com/gw9ZOxw.jpg)

In the screen that shows up, expand OMNeT++, click on Makemake.
Select quisp from the middle and on the right-hand side, choose Makemake and then just click on apply. now we don't need to setup options!


![](https://i.imgur.com/VLCIRbT.jpg)

In the *Project Explorer* right-click on quisp and choose *Run As* > *OMNeT++ Simulation*.



![](https://i.imgur.com/HUqfexW.jpg)


The following window will pop up, and it will take up to 2 mins to get the simulation set up.



![](https://i.imgur.com/UtvHhhy.jpg)


Test the simulation by choosing a *Config name*



![](https://i.imgur.com/7w7tEot.jpg)


And Voilà !!!



![](https://i.imgur.com/CMibCCQ.jpg)


## 4- Running A Simulation

From File > Set Up an Unconfigured Network...



![](https://i.imgur.com/7uDnnZ6.jpg)


Choose a network and click OK.

![](https://i.imgur.com/5GTZ3wO.jpg)


Enjoy the simulated results!!


![](https://i.imgur.com/Uz63F8A.jpg)




## Running interesting simulations

You should now be ready to simulate quantum networks!  Two places
you can go:

* Go to [running demos](running-demos.md).
* Just return to [the top-level readme](../README.md) and check
  options from there.