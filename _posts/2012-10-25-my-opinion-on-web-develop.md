---
layout: post
title: "web开发"
description: ""
category: 
tags: [ror]
---
{% include JB/setup %}
### 前言 ###
前阵子写了一个[数独网站](http://sudo-alexbian.rhcloud.com)，总结一下。使用的平台是redhat公司的Paas,openshift，支持ruby或者ROR组合，支持git部署。
### 跨浏览器开发 ###
这个秘诀在于有一个好的框架封装，如blueprint和jquery（包括封装了ajax），写出的代码可以兼容所有主流的浏览器（旧版ie下有一些不太一样的地方）。光有这些可能还不够，需要更好的整合工具如compass，他整合了很多主流的web前端开发工具，包括刚提到的blueprint，还有sprite，一个图片拼合工具。
### 工具利用 ###
需要不断尝试新的工具来提高生产效率，现在很火的一些语言如python，ruby等都有一个特点，就是代码写的很少，解决的问题却很多。web开发这个领域，有很多语言是用来生成过去的网页语言的（js+css+html），比较流行的是这个组合coffeescript+scss/sass+haml，工作效率会最大化。
### 写测试 ###
rspec即可，rails测试还是非常简单。fixture可以用factorygirl来写。flexmock可以生成mock。需要注意的是mvc每一层都要测试到。cucumber可以用来辅助view的测试。
### 美化 ###
搞web前端的，人人都要成为艺术家，都要有一点强迫症，网页的布局要精通。不要用什么deamweaver，frontpage，shame on you!!网页的布局是有一个清晰的框架的，头脑里是完全可以想象的很细致的。最好的学习方式（我觉得）是用chrome的inspecter功能审查一些著名网站的html框架，可以动态的改变参数来看看配色和框架的改变。还有w3cschool是个很好的学习资源
### 使用Linux开发 ###
如果你是做RoR相关的开发，我推荐用Linux来开发，而且是Arch/Gentoo/Fedora，其他版子的程序更新有点慢。Mac也可以，有textMate可以用。Windows下安装和配置生产环境就会让你蛋痛不已。

