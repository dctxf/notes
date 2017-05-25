# Shell

记录一些常用的shell命令

## scp

不同终端之间传输数据

```bash
scp -r filePath/fileName root@127.0.0.1:filePath/fileName
# -r 递归复制
# 举例 复制本地文件到远端服务器
# scp a.txt root@127.0.0.1:~/demo/a.txt
```