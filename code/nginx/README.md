# Nginx

我的个站是用nginx服务，欢迎大家来瞅瞅

* [门口摔倒的老大爷](htpps://dctxf.com)

## 常见错误

```bash
nginx: [error] open() "/var/run/nginx.pid" failed (2: No such file or directory)
```

解决办法 **停止nginx服务，重启服务就行**

```
sudo service nginx stop
```