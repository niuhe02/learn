git:
----
[Git 使用的简单汇总](http://blog.csdn.net/richardysteven/article/details/5956854)

###显示改动 撤销改动
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
 - 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
 - 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。
 - 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

###版本回退
* HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
* 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
* 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

###远程仓库
要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；
关联后，使用命令git push -u origin master第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；




python:
-------

c
-

c++
---

posix
-----
