---
layout: post
title: "Start My Blog"
description: "this page is write from emacs,and posted by git"
category: 
tags: [footprint]
---
{% include JB/setup %}
Preclude  
----------
  
准备开始动手写个博客，以后思考的时间越来越多，而且现在头脑里整天都在思考问题，感觉写点什么才好。  

关于这个博客  
----------
  
这个博客是利用github提供的免费服务git pages 来创建的，应该是无流量限制的，缺点就是门槛较高。本文用emacs24来编写，结合markdown-mode，highlight-tail-mode，写文章简直是种享受。。。  
关于Markdown  
----------
  

[这里](http://linuxtoy.org/archives/emacs-markdown-mode.html)是个
markdown-mode的快捷键列表,摘抄如下：  

1. **快捷键**    
*   C-c C-t n 插入 hash 样式的标题，其中 n 为 1~5，表示从第一级标题到第五级标题。  
*   C-c C-t t 插入 underline 样式的标题，这是一级。  
*   C-c C-t s 同上，这是二级。  
*   C-c C-a l 插入链接，格式为 \[text\](url)。  
*   C-c C-i i 插入图像，格式为 \!\[text\](url)。  
*   C-c C-s b 插入引用内容。  
*   C-c C-s c 插入代码。  
*   C-c C-p b 加粗。  
*   C-c C-p i 斜体。  
*   C-c - 插入水平线 。  
   如果是在选定的内容上按这些组合键，那么将把选定的内容设为相应的格式。  
   
2.**大纲视图**  
  按 S-Tab 将在大纲视图、目录视图、及正常视图间切换。  
  
3.**预览**  
 
  如果你的系统中安装有 Markdown 程序包的话，那么在 Emacs 中便可以运行 Markdown，并预览其输出。相应命令如下：  
 
*    C-c C-c m 在当前缓冲运行 Markdown，并在另一个缓冲预览。  
*    C-c C-c p 同上，但在浏览器中预览。  
另外，[这里](http://wowubuntu.com/markdown/)有一篇比较详细的简中的markdown介绍文章，看完就会了它的基本语法。文章结尾给出了调试用的markdown各个平台的编辑器  
