# Mysql学习笔记


为了方便学习，我这里用docker安装了数据库。

## 测试环境

```bash
# 下载mysql最新镜像
docker pull mysql

# 新建测试镜像(根据Dockerfile文件)
docker build -t mysql:test .

# 启动容器
docker run --name mysql-test -e MYSQL_ROOT_PASSWORD=123456 -d -p 3306:3306 mysql:test

<!-- 代码解释 -->
--name #容器名 这里为 some-mysql
-e #设置容器中的环境变量
-d #后台启动
-p 3306:3306 #把容器的3306端口映射到主机的3306端口
MYSQL_ROOT_PASSWORD=my-secret-pw #设置mysql的密码为123456
```

## 常用命令

### 数据库连接

```bash
mysql -u root -p
mysql -h 127.0.0.1 -P 3306 -u root -p
```

### 查看命令

```sql
show databases;	// 查看数据库
show tables; 		// 查看表
describe tablename;	// 显示tablename表的描述
flush privileges;	//刷新数据库
describe user;	//显示user表的列信息

select version();current_date;	//显示当前数据库的版本和当前时间

use dbname;	// 切换数据库
```

### 修改数据库密码

```sql
update user set password=password("newPwd123") where user='root';
```

### 数据库备份\导出

```bash
mysqldump -h host -P 3306 -u root -p dbname > 'dbname_backup.sql'
// mysqldump -h 地址 -P 端口 -u 用户 -p 数据库名 > ‘备份sql文件存储地址’
```

### 数据库恢复\导入

```bash
mysql -h host -P 3306 -u root -p dbname 'dbname_backup.sql'
```

## 拓展阅读

[菜鸟教程](http://www.runoob.com/mysql/mysql-data-types.html)




