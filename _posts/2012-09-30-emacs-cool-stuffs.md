---
layout: post
title: "Emacs cool stuffs : highlight-tail"
description: ""
category: geek
tags: [emacs, cool things]
---
{% include JB/setup %}
Prelude
==========
本文介绍一个可以使Emacs变得很sexy的插件highlight-tail。
### 安装 ###

而这款插件可以使每你每输入的一个字符都会有轻微的视觉上的响应，会使得输入emacs的字符的背景颜色产生变化。而且这款插件的资源占用不高，轻量级，只有一个文件。
[这一篇](http://emacser.com/highlight-tail.htm)是我的入门文章的，原文讲解的很细致，足够你配置好了这一款插件，
而且作者的配置，是一种深红色的尾巴，配合monokai主题，very sexy!!

插件的下载可以在**[这里](/multim/highlight-tail.el)**，在添加到可以require的目录里面。

我这里只是说一下如何更改配色,按照上面的蓝色链接装好插件后，将以下lisp代码追加至~/.emacs文件中


	;; tail
	(require 'highlight-tail)
	(highlight-tail-mode t)
	(setq highlight-tail-colors
	'(("black" . 0)
	("#bc2525" . 25)
	("black" . 66)))
	(highlight-tail-mode nil)
	(highlight-tail-mode t)


因为highlight-tail-mode 有一个默认的配色，所以更换其他颜色时，需要禁用在启用，这是最后2行的意思。关于颜色的说明，还是看英文比较好

>   List of colors through which the fading will last.
>   The argument for every color is a percent at which this color
>   will have greatest intensity.

### 我的演示 ###

原作者ahei的演示用的emacs配色不太好看，我这里画蛇添足，重新录制一份，如果显示太小，可以全屏观看

<!-- "Video For Everybody" http://camendesign.com/code/video_for_everybody -->
<p>
	<video controls="controls" width="600" height="400">
	<source src="/multim/h-t-m.ogv" type="video/ogg" />
	<object type="application/x-shockwave-flash" data="http://releases.flowplayer.org/swf/flowplayer-3.2.1.swf" width="800" height="500">
	<param name="movie" value="http://releases.flowplayer.org/swf/flowplayer-3.2.1.swf" />
	<param name="allowFullScreen" value="true" />
	<param name="wmode" value="transparent" />
	<param name="flashVars" value="config={'playlist':[{'url':'','autoPlay':false}]}" />
	<span title="No video playback capabilities, please download the video below"></span>
	</object>
	</video>
	<p>
	<strong>Download video:</strong> <a href="/multim/h-t-m.ogv">Ogg format</a>
	</p>

</p>













