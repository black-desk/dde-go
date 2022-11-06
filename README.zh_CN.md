# DDE的go配置

[English](./READMD.md) | 简体中文

这个项目的目的是快速地为v20版本的深度桌面环境中的所有go语言项目创建开发环境.

由于deepin的go版本卡在了1.15.9,以及其几乎所有桌面环境相关的go项目都不使用gomod进
行构建.在go版本较新的发行版上搭建能让gopls正常工作的开发环境显得有些麻烦.

为了解决这个问题,你需要安装[goenv][==link1==]以及[一些钩子][==link2==].

你可以参考[我的配置][==link3==]来安装和设置goenv,来使上述钩子正常工作.

然后运行:

``` bash
goenv install 1.15.9
./scripts/setup
```

你的go语言开发环境会以传统的GOPATH模式创建在`./.gopath`,GOPATH变量也已经正确地被
配置了.

## 注意

1. 以上配置在此目录外并不会生效,所以你的其他使用gomod的项目仍然可以正常地工作.

2. gopls可能会报告其已经不支持1.15.9,但是目前看起来它工作得挺正常.

3. 由于dde中的项目有使用cgo,你需要自己安装其他的非go语言构建依赖.

[==link1==]: https://github.com/syndbg/goenv
[==link2==]: https://github.com/black-desk/dotfiles/tree/master/private_dot_local/lib/goenv_hook
[==link3==]: https://github.com/black-desk/dotfiles/blob/f6671faf1ffbfdc5542a721f37253a6b61cd0326/dot_zshenv#L50-L63
