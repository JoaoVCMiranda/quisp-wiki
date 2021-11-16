QuISP is now available on Web Browser by WebAssembly(WASM).
Go to [https://aqua.sfc.wide.ad.jp/quisp-online/master/](https://aqua.sfc.wide.ad.jp/quisp-online/master/)
![QuISP Wasm screenshot](https://i.imgur.com/aNcC0n4.png)

We can
* run a QuISP simulation
* pause the simulation and watch the packets
* see the network configuration (.ned files)
* record results of the simulation (e.g bell-pair generation rate)
* download the recording results and analyze them in your OMNeT++ IDE

## Run a simulation

you can choose a simulation config.
![selecting Inifile Configuration](https://i.imgur.com/BFc5W4e.png)

and then, you can run the simulation.
you can 1. step a simulation event, 2. run normally with animation, 3. run fast mode. the "express" mode is not implemented and clicking the "express" button causes a crash. 

then click "ok" to prepare the simulation, it will take a few seconds.

also, you can walk on the network by double-clicking the repeaters, hosts, or network component icons like this.
![](blob:https://imgur.com/f0d1544d-c1ac-4a92-8262-d601a2af2e02)

## Caveat
QuISP on wasm might take CPU resources and memory of your machine. Be careful if your machine is not high-end.

## Watch the packet 

## Result recording