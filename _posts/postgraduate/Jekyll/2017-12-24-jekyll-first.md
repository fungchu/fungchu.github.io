---
layout: post
title: "搭建本地调适环境以及安装jekyll"
data: 2017-12-24 16:45:00 +0800
categories: jekyll
tag: Jekyll
---
* content
{:toc}




1.由于为的mac环境osX上面已经自带的了Ruby的环境，所以直接安装jekyll

2.打开终端，执行 $gem install jekyll

第一次搭建环境的时候完全不知道怎么搞啊，运行的时候一直报错，在网上找了好多方法，有的说要用翻墙啊什么的，最后使用了淘宝镜像解决了。

3.在终端执行 $ jekyll new blog 可以新建一个jekyll生成的blog，当然也可以从网上或者github上找一些别人提供的开源模板，效果都不错，提供一个http://jekyllthemes.org/,用git clone到本地，或者是fork到自己的github上。

4.将本地项目上传到之前建立的github代码仓库上。(注：发布到Github上后可能需要有一段时间的延迟才可以访问)

> * git init
> * git add README.md
> * git commit -m "first commit"
> * git remote add origin GitHub - answershuto/answershuto.github.io: Personal Blog
> * git push -u origin master
5.在浏览器中输入 http://userName.github.io即可,例如http://answershuto.github.io

5.在浏览器中输入 http://userName.github.io即可,例如http://answershuto.github.io
6.本地调试

进入之前jekyll new blog 生成的目录下或者是git clone出来的目录下，

> * $cd blog
> * $jekyll serve
### 在浏览器中输入 localhost:4000    (注：jekyll默认用4000端口，可以在配置中修改该端口号)

接下来就可以愉快地修改自己blog的代码，打造一个自己喜欢风格的blog了
