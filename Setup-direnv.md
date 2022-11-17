1. install https://github.com/direnv/direnv
2. setup https://github.com/direnv/direnv/blob/master/docs/hook.md
3. create `.envrc` like this in your quisp root (here, the root is `/home/user/quisp`)
```sh
PATH_add "/home/user/omnetpp-6.0.1/bin"
PATH_add "/home/user/omnetpp-6.0.1/tools/macosx/bin"
PATH_add "/usr/local/opt/llvm/bin" # if you want
export QT_PLUGIN_PATH=/home/user/omnetpp-6.0.1/tools/macosx/plugins
export QT_SELECT=5
```
4. allow the .envrc: `$　direnv allow`
