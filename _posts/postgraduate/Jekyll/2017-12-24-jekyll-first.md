---
layout: post
title: "如何用jekyll搭建个人博客"
data: 2017-12-24 16:45:00 +0800
categories: 研究生涯
tag: Jekyll
---
* content
{:toc}


这里主要介绍了如何利用jekyll搭建个人博客的教程，若有错误，请指出。

<!-- more -->

### 介绍

通俗一点讲，jekyll是一个简单的免费的Blog生成工具，类似WordPress，是一个轻量级的内容管理系统。但是和WordPress又有很大的不同，原因是jekyll只是一个生成静态网页的工具，不需要数据库支持。jekyll可以免费部署在Github上，而且可以绑定自己的域名。

### 脚本语言

安装jekyll之前，请您先安装好ruby的脚本语言，jekyll也支持 python语言，但是github更支持ruby语言，若您想要上传到github,ruby是个更好的选择。

### 安装Jekyll
```
gem install jekyll
```

### 创建jekyll项目

首先切换到你想要的目录，例如我想切换到桌面，就可以输入以下命令链：

```
cd Desktop
```

如果我想创建的jekyll项目叫myblog,可以输入以下命令链：

```
jekyll new myblog
```
以上执行完之后，应该就可以在对应目录看到一个叫myblog的文件夹，里面就是你个人博客的各种后台文件。
### 运行文件

创建完项目之后，您就可以在powershell中运行myblog的文件，您可以输入以下命令链：

```
jekyll serve
```

运行完之后，您就可以看到一串ip地址，您可以拷贝到浏览器上，就可以看到您自己的个人博客了。