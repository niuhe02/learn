git:
----
[Git 使用的简单汇总](http://blog.csdn.net/richardysteven/article/details/5956854)

显示改动 撤销改动
====================================
- “git diff HEAD -- readme.txt”命令可以查看工作区和版本库里面最新版本的区别
- git diff --staged -- readme 或者 git diff --cached
显示staged改动，也就是add的东东，也就是将要commit的东东和版本库里面最新的区别
- git diff -- readme 查看工作区没有add到暂存区的改动的区别
- 撤销改动
 - git checkout -- file.1
 撤销了file.1的这次改动。只是撤销了没有staged的改动/即没有执行add。中间的 -- 表明了这是一个文件 而不是一个branch的名字 
 - git reset HEAD -- file.1
 撤销了所有没有commit的改动，包括了stage的和没有stage的。
 - 这条命令的结果一样
 git checkout HEAD -- file.1
 包括了staged 和没有staged的都会清除。

###版本回退
* HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
* 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
* 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。




python:
-------

c
-

c++
---

posix
-----
