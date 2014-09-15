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
- 要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；
- 关联后，使用命令git push -u origin master第一次推送master分支的所有内容；
- 此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

- 要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone命令克隆。git clone git@github.com:path/repo-name.git

###创建与合并分支
Git鼓励大量使用分支：
- 查看分支：git branch
- 创建分支：git branch name
- 切换分支：git checkout name
- 创建+切换分支：git checkout -b name
- 合并某分支到当前分支：git merge name
- 删除分支：git branch -d name
合并分支解决冲突
- 当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
- 用git log --graph --pretty=oneline命令可以看到分支合并图。

###分支管理策略
- 通常，合并分支时，如果可能，Git会用“Fast forward”模式，但这种模式下，删除分支后，会丢掉分支信息。
如果要强制禁用“Fast forward”模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。
- git merge --no-ff -m "merge with no-ff" dev
-
在实际开发中，我们应该按照几个基本原则进行分支管理：
- 首先，master分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；
- 那在哪干活呢？干活都在dev分支上，也就是说，dev分支是不稳定的，到某个时候，比如1.0版本发布时，再把dev分支合并到master上，在master分支发布1.0版本；
- 你和你的小伙伴们每个人都在dev分支上干活，每个人都有自己的分支，时不时地往dev分支上合并就可以了。




python:
-------

c
-

c++
---

posix
-----
