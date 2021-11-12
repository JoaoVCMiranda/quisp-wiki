we use OMNeT++5.6.2 primarily, but we want to OMNeT++5.7 and 6 later.

|  OMNeT++  |  Platform                          |  Simulation  |  Unit tests  |  Module tests  |  E2E tests   | 
|  ----     |  ----                              |  ----        |  ----        |       ----     |  ----        |
|  5.6.2    |  Ubuntu 18.04 docker               |      ✅      |    ✅        |          ✅     |  ✅          |
|  5.6.2    |  Ubuntu 21.04                      |      ✅      |    ✅        |          ✅     |  ✅          |
|  5.6.2    |  MacOS 11.6(Intel) docker          |      ✅      |    ✅        |          ✅     |  ✅          |
|  5.6.2    |  MacOS 11.6(Intel)                 |      ✅      |    ✅        |          ✅     |  ✅          |
|  5.6.2    |  MacOS 12.1(M1) docker             |      ❌      |    ✅        |          ✅     | ✅        |
|  5.6.2    |  MacOS 12.1(M1)                    |   (wip)      |    (wip)    |       (wip)     |  (wip)       |
|  5.6.2    |  Windows 11(Intel)                 |      ✅      |    ❌        |        ❌       |  ✅       |
|  5.6.2    |  WebAssembly                       |      ✅      |    ❌        |        ❌       |  ❌       |
|  5.7      |  MacOS 11.6(Intel)                 |   (wip)      |    (wip)    |       (wip)     |  (wip)       |
|  5.7      |  MacOS 11.6(Intel) docker          |     ✅       |    ✅       |       ✅         |  ✅       |
|  5.7      |  MacOS 12.1(M1 x86 mode)           |     ✅       |    ✅        |       ✅        |  ✅       |
|  5.7      |  MacOS 12.1(M1 amd64 mode)         |   (wip)      |    (wip)    |       ✅        |   ✅      |
|  5.7      |  Ubuntu 18.04 docker               |   (wip)      |    (wip)    |       (wip)     |  (wip)       |
|  5.7      |  Ubuntu 21.04                      |     ✅       |    ✅       |         ✅       |  ✅          |
|  5.7      |  Windows 11(Intel)                 |     ✅       |    ❌       |         ❌       |  (wip)       |

## Notes

### MacOS 12.1 M1 docker
GUI doesn't work now
