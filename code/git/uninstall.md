# Git卸载

经常都是安装，突然间碰到卸载git一脸懵逼啊。尝试找了一下方法。结果如下。

```bash
where git

# /usr/local/bin/git
# /usr/bin/git
# /usr/local/git/bin/git
```
我的电脑竟然安装了3个，这还不算，我用homebrew又安装了一个。那么我想用homebrew的怎么办呢？

卸载多余版本，当然如果你没有多余版本就不用看这一步了,因为都需要管理员权限，所以都加上`sudo`

```bash
sudo rm -rf /usr/local/bin/git*
sudo rm -rf /usr/local/git/
```

~~备份自带版本(网上找到的,此法已行不通)~~

```bash
cd /usr/bin
mkdir old-git
# 到这里出问题了，出现以下错误
# mkdir: old-git: Operation not permitted
```

原因是`El Capitan`加入了`Rootless`机制**Rootless机制将成为对抗恶意程序的最后防线**虽然可以关闭`rootless`但是我感觉还是不要吧，毕竟**安全第一**

于是又找办法，运气不错，找到了

```bash
brew link git
```

Done! It's so easy!

什么设置环境变量，一点用都没。还是这个方法靠谱，快来试试。
