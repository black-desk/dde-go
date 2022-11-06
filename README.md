# go for DDE

English | [简体中文](./README.zh_CN.md)

This project is aim to provide a golang develop environment quick setup for
deepin (v20) desktop environment.

As deepin golang version stuck at 1.15.9, and all dde releated golang project do
not use gomod at all, it's quite a little bit hard to setup a workspace to make
gopls working.

You will need [goenv][==link1==] and [some hooks][==link2==] for it.

Try to setup goenv just [like I did][==link3==], to let the hooks work.

Then run:

``` bash
goenv install 1.15.9
./scripts/setup
```

Your go workspace will be ready at GOPATH mode in `./.gopath`, as the GOPATH
environment variable set.

## Note

1. This setup will not take effect when you are out side of this directory. So
   your other gomod-base projects will work just like before.

2. You might recive a warning from gopls for the lastest version of gopls not
   support 1.15.9, but it seems to work fine.

3. As cgo is used in dde, you have to install other non-go build dependencies
   yourself.

[==link1==]: https://github.com/syndbg/goenv
[==link2==]: https://github.com/black-desk/dotfiles/tree/master/private_dot_local/lib/goenv_hook
[==link3==]: https://github.com/black-desk/dotfiles/blob/f6671faf1ffbfdc5542a721f37253a6b61cd0326/dot_zshenv#L50-L63
