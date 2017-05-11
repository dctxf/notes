# DOCKER学习笔记

docker 不做深入学习，基本够用就行。记录一些自己用到的东西。

## 安装

### Mac

Mac安装docker我认为是最简单的。因为去官网下载个客户端，跟普通软件一样。

[下载地址](https://www.docker.com/docker-mac)

### Centos

文档上说centos需要最低centos7，不知道为什么我的centos6也安装成功了。这里只列出安装方法，有问题的童鞋自行Google

#### CentOS 7

Docker（重新编译自 RHEL 7）已收录在 CentOS-Extras 软件库内。你只须执行

```bash
sudo yum install docker
```

要是你想采用一个（普遍）较新版的 docker，你可以加入以下软件库：

```bash
[virt7-docker-common-candidate]
name=virt7-docker-common-candidate
baseurl=https://cbs.centos.org/repos/virt7-docker-common-candidate/x86_64/os/
enabled=1
gpgcheck=0
```

> 注：你或许需要停用 CentOS-Extras 以确保是组件是来自虚拟化 SIG 软件库。

```bash
sudo yum install docker --disablerepo=extras
```

安装 docker 后，你必须引导该服务才能应用它。

```bash
sudo systemctl start docker
```

若要开机时引导 docker 服务：

```bash
sudo systemctl enable docker
```

#### CentOS 6

> 在 CentOS-6 上安装 Docker 须要采用 [EPEL](https://fedoraproject.org/wiki/EPEL) 软件库。启用 EPEL 后，你便能继续以下的安装程序

要在 CentOS-6 上安装 docker，请利用以下指令安装 docker-io 组件：

```bash
sudo yum install docker-io
```

安装 docker 后，你必须引导该服务才能应用它。

```bash
sudo service docker start
```

若要开机时引导 docker 服务：

```bash
sudo chkconfig docker on
```

## 安装镜像 images

```bash
docker pull 镜像名
```

## 加速器

尝试了，在国内不用加速器，那速度...原因你懂的。

- [阿里云加速器](https://cr.console.aliyun.com/#/accelerator)
- [DaoCloud 加速器](https://www.daocloud.io/mirror#accelerator-doc)

## 常用命令

```bash
docker images //列出本地镜像

docker ps 	//列出真正运行的容器
docker ps -a 	//列出所有容器

dcoker start 容器名or容器id 	//启动一个容器
dcoker stop 容器名or容器id 	//停止一个容器

docker rmi 镜像ID 	//删除镜像
docker rm 容器名or容器ID 	//删除一个已停止运行的容器
docker rm -f 容器名or容器ID 	//强制删除一个容器
```

## 拓展阅读
- [Docker官网](https://www.docker.com/)
- [Docker从入门到实践](https://yeasy.gitbooks.io/docker_practice/content/image/build.html)
- [centos docker](https://wiki.centos.org/zh/Cloud/Docker)