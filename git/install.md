# 如何在CentOS 6.x/7.x上安装git及最新版

## yum安装

```bash
yum install git
```

通过yum方式安装，版本比较旧，CentOS6.5上安装好是1.7.1版。如果想安装最新版或其他版本，需要使用源码编译安装的方式。

## 源码包安装

安装依赖包

```bash
yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel
yum install  gcc perl-ExtUtils-MakeMaker
```

卸载旧的git版本（如果之前有安装rpm包）

```bash
yum remove git
```

下载&解压

```bash
cd /usr/src
wget https://www.kernel.org/pub/software/scm/git/git-2.5.0.tar.gz
tar -zxvf git-2.5.0.tar.gz
```

或 

```bash
wget https://github.com/git/git/archive/v2.5.0.tar.gz
```

步骤4. 编译安装

```bash
cd git-2.5.0
make prefix=/usr/local/git all
make prefix=/usr/local/git install
echo "export PATH=$PATH:/usr/local/git/bin" >> /etc/bashrc
source /etc/bashrc
```
检查git版本

```bash
git --version
# git version 2.5.0
```
