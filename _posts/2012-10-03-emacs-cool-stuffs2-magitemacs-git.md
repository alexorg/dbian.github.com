---
layout: post
title: "Emacs cool stuffs(2): Magit,emacs 的git插件"
description: ""
category: geek
tags: [emacs, cool things]
---
{% include JB/setup %}
## Prelude
本文将会介绍emacs的git辅助插件之一——magit。
## 特性
可视化编辑，所有更改都会列在一个独立窗口里，直接在每个更改的状态条上
按快捷键即可，免去反复运行重复的命令，用单个字母即可发布命令，
如`P`表示从远端拉取合并最新更改，`s`表示将文件更改加入stage，
或者将未跟踪的文件加入stage，是利器啊利器。
## 图文介绍常用指令
`M-x magit-status` 打开magit状态buffer，在这里是所有操作的入口   
![](/img/2012-10-03 11:49:37.png)   
对于更改的文件，以及未track的文件，在文件那一条点击，激活后会高亮显示，按`s`即可加入stage，或者按`S`可加入所有更改，他们会进入 Staged changes   
![](/img/2012-10-03 2.png)   
直接按`c`即可将创建新的commit，会提示你在新窗口里输入这次更新的log，按`C-c`即可保存并退出   
![](/img/2012-10-03 3.png)   
连按2个`P`，即可自动的发送到远端仓库了，可以按`$`来随时查看输出

### 在举个有用的栗子
如果有change需要暂时存起来，需要使用stash功能，   
__这个功能是在拉取远端，与本地更改发生冲突时，最好的解决方法__   
![](/img/2012-10-03 4.png)   
按`G`先刷新一下，查看更改，对更改的文件上按`z`，即可创建一个stash，它实际上是一个diff，对于stash随时可以丢掉或者拿出来应用更改。   
__注意__：stash之后本地的改动都会消失   
![](/img/2012-10-03 5.png)   
如何取出来回放呢，按`A`即可，把之前的更改都给我回放一遍吧：）

### 结尾
正如Magit的名字一样，Magit会像变魔术（magic）一样把git的功能发挥的淋漓尽致。   
__注意__：用久了你会离不开它的。。。

__最后附上一张magit快捷键列表__

---

## Magit快捷键列表


<p>

<style type="text/css">

  html {font-family: Times, serif; font-size: 90%;}
  .preamble {font-variant: italic; margin-bottom:40px;}
  .title {text-align: center;}

  h9 {
	  margin-bottom:1px;
      font-variant: small-caps;
	  font-size:1.5em;      
	  text-align:center;
  }

  table {border: 0px solid transparent; width:100%;}
  td {border-collapse:collapse; border: 1px solid #fff;}
  td, th {vertical-align: top;}
  td.command, td.description, td.notes {background-color: #F0E4E4;}
  td.command, td.description {white-space: nowrap;}
  td.command {font-family:monospace; font-size: 130%; font-weight: 600; width:10em;}
  td.notes {color: #666; font-variant: italic;}

</style>
<h9><a name="sec-1">Buffers</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">M-x magit-status</td><td class="description">Magit's status buffer</td><td class="notes">The main entry point to Magit, and the context where the commands described in this cheatsheet are meant to be executed. Probably a good idea to bind magit-status to a key.</td></tr>
<tr><td class="command">$</td><td class="description">magit-process buffer</td><td class="notes">Behind-the-scenes. Displays the git command and its output.</td></tr>
<tr><td class="command">g</td><td class="description">reload status buffer</td><td class="notes">Necessary to update an existing Magit status buffer after saving a file in emacs, or after making changes to repo outside of emacs.</td></tr>
</tbody>
</table>





<h9><a name="sec-2">Section Visibility</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">TAB</td><td class="description">Toggle visibility of current section</td><td class="notes"></td></tr>
<tr><td class="command">S-TAB</td><td class="description">Toggle visibility of current section and its children</td><td class="notes"></td></tr>
<tr><td class="command">1,2,3,4</td><td class="description">Expand current section to the corresponding level of detail - 1, 2, 3 or 4</td><td class="notes">e.g., 4 will show all detail for the current section.</td></tr>
<tr><td class="command">M-1,2,3,4</td><td class="description">Expand all sections to the corresponding level of detail - 1, 2, 3 or 4</td><td class="notes">e.g., M-4 will show all detail for the entire buffer.</td></tr>
</tbody>
</table>




<h9><a name="sec-3">Untracked Files</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">s</td><td class="description">Add untracked file to staging area</td><td class="notes"></td></tr>
<tr><td class="command">i</td><td class="description">Add file to .gitignore</td><td class="notes"></td></tr>
<tr><td class="command">C-u i</td><td class="description">Prompt for file/directory to add to .gitignore</td><td class="notes"></td></tr>
<tr><td class="command">I</td><td class="description">Add file to .git/info/exclude instead of .gitignore</td><td class="notes"></td></tr>
</tbody>
</table>




<h9><a name="sec-4">Staging and Committing</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">s</td><td class="description">Stage current hunk</td><td class="notes">If point is in diff header, will stage all hunks belonging to current diff. If a region is active, only lines in that region will be staged. This is a distinct improvement on the conventional 'git add -p', the splitting mechanics of which are... 'imperfect'.</td></tr>
<tr><td class="command">u</td><td class="description">Unstage current hunk</td><td class="notes">As with s command, only in reverse: diff headers and regions provide a corresponding context to the unstage action.</td></tr>
<tr><td class="command">S</td><td class="description">Stage all hunks</td><td class="notes"></td></tr>
<tr><td class="command">U</td><td class="description">Unstage all hunks</td><td class="notes"></td></tr>
<tr><td class="command">k</td><td class="description">Discard uncommitted changes</td><td class="notes">As with s command.</td></tr>
<tr><td class="command">c</td><td class="description">Prepare for commit</td><td class="notes">Pops up <b>magit-log-edit</b> buffer. to allow you to enter your commit message.</td></tr>
<tr><td class="command">C-c C-c</td><td class="description">Execute commit</td><td class="notes">Actually triggers commit action. Fire this inside the <b>magit-log-edit</b> commit message buffer. To postpone the commit for later, just C-x b to a different buffer and come back to this buffer when you're ready,</td></tr>
<tr><td class="command">C-c C-a</td><td class="description">Make the next commit an amend</td><td class="notes"></td></tr>
</tbody>
</table>




<h9><a name="sec-5">History</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">l</td><td class="description">History</td><td class="notes">Shows terse history for repository.</td></tr>
<tr><td class="command">L</td><td class="description">Verbose history</td><td class="notes"></td></tr>
<tr><td class="command">C-u l</td><td class="description">History segment</td><td class="notes">Will prompt for beginning and end points.</td></tr>
<tr><td class="command">RET</td><td class="description">Inspect commit</td><td class="notes">Shows full information for commit and move point into the new buffer.</td></tr>
<tr><td class="command">a</td><td class="description">Stage current commit on your current branch</td><td class="notes">Useful to cherrypick changes while browsing an alternative branch. Cherrypicked changes need to be committed manually.</td></tr>
<tr><td class="command">A</td><td class="description">Commit current commit on your current branch</td><td class="notes">As with 'a', but will automatically commit changes when there aren't any conflicts.</td></tr>
<tr><td class="command">C-w</td><td class="description">Copy sha1 of current commit into kill ring</td><td class="notes"></td></tr>
<tr><td class="command">=</td><td class="description">Show differences between current and marked commits</td><td class="notes"></td></tr>
<tr><td class="command">..</td><td class="description">Mark current commit</td><td class="notes"></td></tr>
<tr><td class="command">.</td><td class="description">Unmark current commit if marked</td><td class="notes"></td></tr>
<tr><td class="command">C-u ..</td><td class="description">Unmark marked commit from anywhere</td><td class="notes"></td></tr>
</tbody>
</table>





<h9><a name="sec-6">Reflogs</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">h</td><td class="description">Browse reflog from HEAD</td><td class="notes">Reflog buffer works just like History buffer described above.</td></tr>
<tr><td class="command">H</td><td class="description">Browse reflog from chosen point</td><td class="notes"></td></tr>
</tbody>
</table>





<h9><a name="sec-7">Diffing</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">d</td><td class="description">Show changes between working tree and HEAD</td><td class="notes"></td></tr>
<tr><td class="command">D</td><td class="description">Show changes between two arbitrary revisions</td><td class="notes"></td></tr>
<tr><td class="command">a</td><td class="description">Apply current changes to working tree</td><td class="notes">Change-selection works as described in 'Staging and Committing' above.</td></tr>
<tr><td class="command">v</td><td class="description">Apply current changes to working tree in reverse</td><td class="notes"></td></tr>
</tbody>
</table>




<h9><a name="sec-8">Tagging</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">t</td><td class="description">Make lightweight tag</td><td class="notes"></td></tr>
<tr><td class="command">T</td><td class="description">Prepare annotated tag</td><td class="notes">Launches <b>magit-log-edit</b> buffer for writing annotation.</td></tr>
<tr><td class="command">C-c C-c</td><td class="description">Commit annotated tag</td><td class="notes">Actually triggers annotated tag action.</td></tr>
</tbody>
</table>





<h9><a name="sec-9">Resetting</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">x</td><td class="description">Reset your current head to chosen revision</td><td class="notes">No changes will be made to working tree or staging area. Typing x while point is in a line describing a commit will offer this commit as the default revision to reset to.</td></tr>
<tr><td class="command">X</td><td class="description">Reset working tree and staging area to most recent committed state</td><td class="notes">Destructive! Will discard all local modifications.</td></tr>
</tbody>
</table>





<h9><a name="sec-10">Stashing</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">z</td><td class="description">Create new stash</td><td class="notes">Stashes are listed in the status buffer.</td></tr>
<tr><td class="command">Z</td><td class="description">Create new stash and maintain state</td><td class="notes">Leaves current changes in working tree and staging area.</td></tr>
<tr><td class="command">RET</td><td class="description">View stash</td><td class="notes"></td></tr>
<tr><td class="command">a</td><td class="description">Apply stash</td><td class="notes"></td></tr>
<tr><td class="command">A</td><td class="description">Pop stash</td><td class="notes"></td></tr>
<tr><td class="command">k</td><td class="description">Drop stash</td><td class="notes"></td></tr>
</tbody>
</table>





<h9><a name="sec-11">Branching</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">b</td><td class="description">Switch to different branch</td><td class="notes">Current branch is indicated in header of status buffer.</td></tr>
<tr><td class="command">B</td><td class="description">Create and switch to new branch</td><td class="notes"></td></tr>
</tbody>
</table>




<h9><a name="sec-12">Wazzup</a></h9>


<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">w</td><td class="description">Show summary of how other branches relate to current branch</td><td class="notes"></td></tr>
<tr><td class="command">i</td><td class="description">Toggle ignore branch</td><td class="notes"></td></tr>
<tr><td class="command">C-u w</td><td class="description">Show all branches including ignored ones</td><td class="notes"></td></tr>
</tbody>
</table>



<h9><a name="sec-13">Merging</a></h9>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">m</td><td class="description">Initiate manual merge</td><td class="notes">Applies all changes to working area and index, without committing.</td></tr>
<tr><td class="command">M</td><td class="description">Initiate automatic merge</td><td class="notes">Applies all changes to working area and index. Commits changes immediately.</td></tr>
</tbody>
</table>



<h9><a name="sec-14">Rebasing</a></h9>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">R</td><td class="description">Initiate or continue a rebase</td><td class="notes"></td></tr>
</tbody>
</table>



<h9><a name="sec-15">Rewriting</a></h9>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">r s</td><td class="description">Start a rewrite</td><td class="notes"></td></tr>
<tr><td class="command">v</td><td class="description">Revert a given commit</td><td class="notes"></td></tr>
<tr><td class="command">r t</td><td class="description">Remove bookkeeping information from buffer</td><td class="notes"></td></tr>
<tr><td class="command">r a</td><td class="description">Abort rewriting</td><td class="notes"></td></tr>
<tr><td class="command">r f</td><td class="description">Finish rewriting</td><td class="notes">Applies all unused commits.</td></tr>
<tr><td class="command">r *</td><td class="description">Toggle the * mark on a pending commit</td><td class="notes"></td></tr>
<tr><td class="command">r ..</td><td class="description">Toggle the . mark on a pending commit</td><td class="notes"></td></tr>
</tbody>
</table>



<h9><a name="sec-16">Pushing and Pulling</a></h9>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">P</td><td class="description">git push</td><td class="notes">Uses default remote repository.</td></tr>
<tr><td class="command">C-u P</td><td class="description">git push to specified remote repository</td><td class="notes"></td></tr>
<tr><td class="command">f</td><td class="description">git remote update</td><td class="notes"></td></tr>
<tr><td class="command">F</td><td class="description">git pull</td><td class="notes"></td></tr>
</tbody>
</table>



<h9><a name="sec-17">Interfacing with Subversion</a></h9>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<COL align="left"><COL align="left"><COL align="left">
<tbody>
<tr><td class="command">N r</td><td class="description">git svn rebase</td><td class="notes"></td></tr>
<tr><td class="command">N c</td><td class="description">git svn dcommit</td><td class="notes"></td></tr>
</tbody>
</table>
</p>
