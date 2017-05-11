# Mysql学习笔记


为了方便学习，我这里用docker安装了数据库。

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
mysqldump -h host -p 3306 -u root -p dbname > dbname_backup.sql
// mysqldump -h 地址 -P 端口 -u 用户 -p 数据库名 > ‘备份sql文件存储地址’
```

数据库恢复\导入

```bash

```


## 拓展阅读

[菜鸟教程](http://www.runoob.com/mysql/mysql-data-types.html)




