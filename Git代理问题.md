## 问题描述

从本地提交代码到 GitHub 远程仓库，由于 DNS 污染的问题，国内提交速度很慢，有时候还报错。笔者自己花钱买了一个梯子，但开启梯子的代理后仍然没有解决问题，不过 Google 等倒是可以访问了。

## 原因分析

虽然开启了代理，但可能 git push 并没有走代理，因为需要在 git 里面进行配置。

## 解决方法

配置 git push 直接走[网络代理](https://so.csdn.net/so/search?q=网络代理&spm=1001.2101.3001.7020)：

```bash
git config --global http.proxy socks5://127.0.0.1:1080
git config --global https.proxy socks5://127.0.0.1:1080
12
```

其中 1080 是 SOCKS 代理的端口，一般默认 1080，可以在代理工具的设置中查看。