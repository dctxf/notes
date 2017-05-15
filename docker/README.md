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

## 命令

### 常用

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
### 用于与容器交互的命令

```bash
docker create  # 创建一个容器，但不启动它
docker run     #  创建并启动一个容器
docker stop    # 停止容器
docker start   #  启动容器
docker restart # 重启容器
docker rm      # 删除容器
docker kill    #  给容器发送kill信号
docker attach  # 连接到正在运行的容器中
docker wait    # 阻塞直到容器停止为止
docker exec    # 在运行的容器中执行一条命令
```

### 检查容器

```bash
docker ps      # 显示运行的容器
docker inspect # 显示容器信息（包括ip地址）
docker logs    # 获取容器中的日志
docker events  # 获取容器事件
docker port    # 显示容器的公开端口
docker top     # 显示容器中运行的进程
docker diff    # 查看容器文件系统中改变的文件
docker stats   # 查看各种纬度数据、内存、CPU、文件系统等
```

## 参数解释

```bash
docker run -it --rm -d ubuntu
--interactive (-i) #将标准输入发送给进程
-tty (-t) #告诉进程有终端连接。 这个功能会影响程序的输出和它如何处理Ctrx-C等信号。
--rm #退出时删除镜像。
-d #后台运行

docker run --name mydb --env MYSQL_USER=db-user -e MYSQL_PASSWORD=secret --env-file ./mysql.env mysql

--name #给容器命名， 否则它是一个随机容器
--env （-e）#设置容器中的环境变量
--env-file #从env-file中引入所有环境变量（同Linux下的source env-file 功能）
mysql #指定镜像名为 mysql:lastest
```

```bash
# 发布容器的80端口到主机上的随机端口
docker run -p 80 nginx

# 发布容器端口80和主机上的8080端口
docker run -p 8080:80 nginx

# 发布容器80端口到主机127.0.0.0.1的8080端口
docker run -p 127.0.0.1:8080:80 nginx

# 发布所有容器中暴露的端口到主机的随机端口上
docker run -P nginx
```

## 拓展阅读
- [Docker官网](https://www.docker.com/)
- [Docker从入门到实践](https://yeasy.gitbooks.io/docker_practice/content/image/build.html)
- [centos docker](https://wiki.centos.org/zh/Cloud/Docker)