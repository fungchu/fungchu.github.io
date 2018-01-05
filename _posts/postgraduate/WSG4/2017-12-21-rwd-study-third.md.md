---
layout: post
title: "Liquid基础语法"
date: 2017-12-21 11:00:00 +0800 
categories: rwd
tag: Liquid
---
* content
{:toc}
## 写作目的
最近很多同学在修改jekyll模板过程中，都不免会接触一些Liquid语法，所以我将一些Liquid的基础语法整理出来，希望能帮到大家。
<!-- more -->
## 基本介绍
liquid 代码可以被分类为对象，标签和过滤代码
### 对象
对象表示页面中将要显示的内容，对象和变量使用双花括号表示
### 标签
标签创建模板的逻辑和控制流，标签使用花括号和百分号表示
标签的使用不会产生其他的文本，即说明在页面中不显示liquid逻辑代码的条件下，我们可以分配变量，创建条件和循环。
存在三种类型的标签，控制流标签，迭代型标签，变量赋值型标签
Standard Filters标准过滤器
ate -时间格式化
1. capitalize-设置输入中的某个单词*
1. downcase-将输入的字符串转换为小写*
1. upcase-将输入的字符串转换为大写
1. first-获得传入的数组的第一个元素
1. last-获得传入的数组的最后一个元素
1. join-用数组的分隔符连接数组中的元素
1. sort-数组中的元素排序
1. map-通过指定的属性过滤数组中的元素
1. size-返回一个数组或字符串的大小
1. escape-转义一个字符串
1. escape_once-返回HTML的转义版本，而不会影响现有的实体转义
1. strip_html-从字符串去除HTML
1. strip_newlines -从字符串中去除所有换行符（\ n）的
1. newline_to_br-用HTML标记替换每个换行符（\ n）
1. replace-替换，例如：{{ 'foofoo' | replace:'foo','bar' }} #=> 'barbar'
1. replace_first-替换第一个，例如： '{{barbar' | replace_first:'bar','foo' }} #=> 'foobar'
1. remove-删除，例如：{{'foobarfoobar' | remove:'foo' }} #=> 'barbar'
1. remove_first-删除第一个，例如：{{ 'barbar' | remove_first:'bar' }} #=> 'bar'
1. truncate-截取字符串到第x个字符
1. truncatewords-截取字符串到第x个词
1. prepend-前置添加字符串，例如：{{ 'bar' | prepend:'foo' }} #=> 'foobar'
1. append-后置追加字符串，例如：{{'foo' | append:'bar' }} #=> 'foobar'
1. minus-减法，例如：{{ 4 | minus:2 }} #=> 2
1. plus-加法，例如：{{'1' | plus:'1' }} #=> '11', {{ 1 | plus:1 }} #=> 2
1. times-乘法，例如：{{ 5 | times:4 }} #=> 20
1. divided_by-除法，例如：{{ 10 | divided_by:2 }} #=> 5
1. split-通过正则表达式切分字符串为数组，例如：{{"a~b" | split:"~" }} #=> ['a','b']
1. modulo-取模，例如：{{ 3 | modulo:2 }} #=> 1

## 标记
目前支持的标记的列表：

1. assign -将某个值赋给一个变量
1. capture-标记文本赋值给一个变量
1. case-标准的case...when代码块
1. comment-块标记，注释掉该块中的文本
1. cycle-通常在循环中使用的值之间交替，如颜色或DOM类。
1. for-for循环
1. if-标准的if/else代码块
1. include -包含另外一个模版
1. raw-暂时停用标签处理以避免出现语法冲突
1. unless-if的反义词