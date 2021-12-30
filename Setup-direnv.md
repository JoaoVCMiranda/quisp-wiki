1. install https://github.com/direnv/direnv
1. create `.envrc` like this in your quisp root (here, the root is `/home/user/quisp`)
```sh
PATH_add "/home/user/omnetpp-5.7/bin"
PATH_add "/home/user/omnetpp-5.7/tools/macosx/bin"
PATH_add "/usr/local/opt/llvm/bin" # if you want
export QT_PLUGIN_PATH=/home/user/omnetpp-5.7/tools/macosx/plugins
export QT_SELECT=5
```
1. allow the .envrc: `$　direnv allow`
