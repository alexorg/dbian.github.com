---
layout: post
title: "使用bitbucket来创建静态网站"
description: ""
category: geek
tags: [web]
---
{% include JB/setup %}
## 前言
今天在想，github作为源码托管网站提供了静态网站的托管服务，那同样是源码
托管的bitbucket是不是也有同样的服务呢，翻了若干遍的bitbucket的在线文档，
终于在一个小角落里，看到了一个[website page host](https://confluence.atlassian.com/display/BITBUCKET/Publishing+a+Website+on+Bitbucket)的服务。
## 如何使用
这个跟github流程差不多，我挑主要的说一下就行，不懂的可以在下面留言，我
们一起讨论。
1. 申请[bitbucket](https://bitbucket.org/)帐号。
2. 在个人帐号页面上绑定ssh密钥，用于git使用ssh传输文件。或者跳过这步，
使用bitbucket特有的https传输，不过这个稍显麻烦之处在于每次都要输入帐号和密
码。
3. 创建一个repo，也就是源码仓库，__仓库名称为__`你的bitbucket帐号
名.bitbucket.com`,（类似于github）建议申请为私有的，这样别人就不可以fork
你的整个网站了。这一点来说，比github把你网站“完全暴露在空气当中”强多
了。
4. 好了，可以用git来clone下你的站点了，clone下来是个空的repo，往里面写
你的主页测试一下吧，在clone到本地的源码下运行终端，运行`echo
"alexbian!" > index.html && git push origin master`试试，bitbucket网站
会立刻更新的。

## 评价
比起github的300M的空间，bitbucket提供的慷慨的1Gb的容量，而且仓库可以设
为私有的，这意味着别人不能fork你的网站或者repo，对隐私敏感的人是有很
大帮助的，我的一些不开源的项目都是免费托管到它上面的。   
不过缺点也是显而易见的，它不提供在线的jekyll，python,php等在线服务，所
以只能事先在本地写好一个静态网站，然后用git传上去。不过这个缺点可以用
写脚本自动的完成的方法克服掉。将网站的源码独立出来托管。

不管怎么样，还是感谢github，bitbucket等网站提供这么优质的服务，希望大
家能够善用但不要滥用这些资源。

