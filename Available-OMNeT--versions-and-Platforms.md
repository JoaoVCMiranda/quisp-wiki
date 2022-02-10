we use OMNeT++5.7 primarily, but we want to move to 6 later.

|  OMNeT++  |  Platform                          |  Simulation  |  Unit tests  |  Module tests  |  E2E tests   |  commit  |
|  ----     |  ----                              |  ----        |  ----        |       ----     |  ----        | ----   |
|  5.7    |  [WebAssembly](https://aqua.sfc.wide.ad.jp/quisp-online/master/)                       |      ✅      |    ❌        |        ❌       |  ❌       |  PR[#380](https://github.com/sfc-aqua/quisp/pull/380)  |
|  5.7      |  MacOS 11.6(Intel)                 |      ❌      |    ❌        |       ❌       |    ❌       |    |
|  5.7      |  MacOS 12.0.1(Intel)               |      ✅      |    ✅        |       ✅     |  ✅        |    |
|  5.7      |  MacOS 11.6(Intel) docker          |     ✅       |    ✅       |       ✅         |  ✅       |    PR[#308](https://github.com/sfc-aqua/quisp/pull/308)   |
|  5.7      |  MacOS 12.1(M1 x86 mode)           |     ✅       |    ✅        |       ✅        |  ✅       |    |
|  5.7      |  MacOS 12.1(M1 arm64 mode)         |     ❌      |     ❌    |          ❌        |   ❌      |    |
|  5.7      |  Ubuntu 18.04 docker               |   (wip)      |    (wip)    |       (wip)     |  (wip)       |    |
|  5.7      |  Ubuntu 20.04                      |     ✅       |    ✅       |         ✅       |  ✅          |    |
|  5.7      |  Windows 11(Intel)                 |     ✅       |    ✅        |         ❌       |  (wip)       |    |
|  5.6.2    |  [WebAssembly](https://aqua.sfc.wide.ad.jp/quisp-online/master/)                       |      ✅      |    ❌        |        ❌       |  ❌       |  PR[#303](https://github.com/sfc-aqua/quisp/pull/303)  |
|  5.6.2    |  Ubuntu 18.04 docker               |      ✅      |    ✅        |          ✅     |  ✅          |    |
|  5.6.2    |  Ubuntu 20.04                      |      ✅      |    ✅        |          ✅     |  ✅          |    |
|  5.6.2    |  MacOS 11.6(Intel) docker          |      ✅      |    ✅        |          ✅     |  ✅          |    |
|  5.6.2    |  MacOS 11.6(Intel)                 |      ✅      |    ✅        |          ✅     |  ✅          |    |
|  5.6.2    |  MacOS 12.1(M1) docker             |      ❌      |    ✅        |          ✅     | ✅        |    |
|  5.6.2    |  MacOS 12.1(M1)                    |   ❌      |    ❌    |       ❌    |  ❌       |    |
|  5.6.2    |  Windows 11(Intel)                 |      ✅      |    ✅         |        ❌       |  ✅       |    |
## Notes

### MacOS 12.1 M1 docker
* OMNeT++5.6.2
  * GUI doesn't work now

OMNeT++5.7 docker is not provided, but I made it, so later will give it a shot.
