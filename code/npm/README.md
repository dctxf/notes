# [NPM](https://www.npmjs.com/)

## 安装

npm会跟node一起安装，如果你不小心把npm给删了，那么别费劲找单独安装方法了。直接重装node得了。

## 升级

### 升级到特定版本

```bash
npm install -g npm@4.0.0
# npm install -g npm@版本号
```

### 升级到最新版本

```bash
npm install -g npm
```

## 其他常用命令

```bash
npm init   # 初始化npm项目 会新建package.json文件
npm install  # 安装依赖 后可跟包名即安装特定包
npm update  # 升级依赖 后可跟包名
npm -v   # 查看npm版本

<!-- 下面命令的效果是一样的 -->
npm view 的别名
npm info react
npm show react
npm v react
```

## 拓展阅读

* [npm 模块安装机制简介](http://www.ruanyifeng.com/blog/2016/01/npm-install.html)