---
layout: post
title: "解决This content should also be served over HTTPS"
date: 2017-12-25 23:00:00 +0800 
categories: 研究生涯
tag: https
---
* content
{:toc}

HTTPS 是 HTTP over Secure Socket Layer，以安全为目标的 HTTP 通道，所以在 HTTPS 承载的页面上不允许出现 http 请求，一旦出现就是提示或报错：

<!-- more -->

```
Mixed Content: The page at 'https://domain.com/w/a?id=074ac65d-70db-422d-a6d6-a534b0f410a4' was loaded over HTTPS, but requested an insecure image 'http://img.domain.com/images/2016/5/3/2016/058c5085-21b0-4b1d-bb64-23a119905c84_cf0d97ab-bbdf-4e25-bc5b-868bdfb581df.jpg'. This content should also be served over HTTPS.
```

很多运营对 https没有技术概念，在填入的数据中不免出现http的资源，出现疏忽和漏洞也是不可避免的。

### 办法一：CSP设置upgrade-insecure-requests
W3C工作组考虑到了我们升级HTTPS的艰难，在2015年4月份就出了一个Upgrade Insecure Requests 的草案（http://www.w3.org/TR/mixed-content/），
他的作用就是让浏览器自动升级请求。在我们服务器的响应头中加入：

```
server {
  ...
  add_header Content-Security-Policy upgrade-insecure-requests;
  ...
}
```
我们的页面是 https 的，而这个页面中包含了大量的 http 资源（图片、iframe等），页面一旦发现存在上述响应头，会在加载 http 资源时自动替换成 https 请求。

### 方法二:页面中加入 meta 头：


```
<meta http-equiv="Content-Security-Policy" content="upgrade-insecure-requests" />
```

目前支持这个设置的还只有 chrome 43.0，不过我相信，CSP 将成为未来 web 前端安全大力关注和使用的内容。而 upgrade-insecure-requests 草案也会很快进入 RFC 模式。