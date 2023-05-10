# 初来乍到

首先投递简历并通过负责人微信，表明求职意向后进入 openEuler RISC-V SIG 微信群。

入群后会有两个任务：

1. 搭建 openEuler RISC-V 的 qemu-system环境
2. 使用 osc 和 obs-build 构建 coreutils（或者别的什么包，主要是为了帮你熟悉流程）

其中，你需要：

```bash
vim ~/.config/osc/oscrc
```

将 apiurl 修改为 https://build.openeuler.openatom.cn 。

## 修改仓库中的包

访问[仓库](https://build.tarsier-infra.com/)，仍然是注册修改apiurl和登录。

修改 `_service`，`osc ci -m "..."`，在你个人的respositories中打上“Publish Flag”，然后就可以在[这里](http://obs-backend.tarsier-infra.com:82/home:/)获取你使用在线构建打好的包。

> 注意：如果要修改“CFLAGS”并且仍然提供debuginfo，你需要确保自己添加了`-g`，不然会报错 %file ... debuginfo.txt 缺失。