# git使用命令

# 基本命令
## 1. git init 
通过命令把这个目录变成git可以管理的仓库
  
## 2. git push origin master
只要本地作了提交，就可以通过上面命令：
把本地master分支的最新修改推送到github上了，现在你就拥有了真正的分布式版本库了。

## 3.git add readme.txt添加到暂存区里面去

## 4. 用命令git commit告诉Git，把文件提交到仓库。

## 5.通过命令git status来查看状态

# 版本回退

## git log命令显示从最近到最远的显示日志，我们可以看到最近三次提交

## git reset --hard HEAD^ 那么如果要回退到上上个版本只需把HEAD^ 改成 HEAD^^ 以此类推

## 我们可以通过版本号回退，使用命令方法如下：git reset --hard 版本号
## 可以通过如下命令即可获取到版本号：git reflog

## git checkout -- file 可以丢弃工作区的修改
命令 git checkout --readme.txt 意思就是，把readme.txt文件在工作区做的修改全部撤销，这里有2种情况，如下：
1.readme.txt自动修改后，还没有放到暂存区，使用 撤销修改就回到和版本库一模一样的状态。
2.另外一种是readme.txt已经放入暂存区了，接着又作了修改，撤销修改就回到添加暂存区后的状态。
 
# 删除与恢复文件

## rm filename
如果我想彻底从版本库中删掉了此文件的话，可以再执行commit命令 提交掉

只要没有commit之前，如果我想在版本库中恢复此文件如何操作呢？

可以使用如下命令 git checkout -- b.txt

Git2.23版本中，已经使用了新命令“git restore”来替代“git checkout”的文件恢复功能

# 远程仓库

## 添加远程库
现在，我们根据GitHub的提示，在本地的testgit仓库下运行命令：

git remote add origin https://github.com/AigoLee/testgit.git

## 把本地库的内容推送到远程，使用 git push命令，实际上是把当前分支master推送到远程。
从现在起，只要本地作了提交，就可以通过如下命令：

git push -u origin master

把本地master分支的最新修改推送到github上了

由于远程库是空的，我们第一次推送master分支时，加上了 –u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令

## 克隆远程库

git clone url
在我本地目录下 生成目录了

# 创建与合并分支
在 版本回填退里，你已经知道，每次提交，Git都把它们串成一条时间线，这条时间线就是一个分支。截止到目前，只有一条时间线，在Git里，这个分支叫主分支，即master分支。HEAD严格来说不是指向提交，而是指向master，master才是指向提交的，所以，HEAD指向的就是当前分支。

git checkout 命令加上 –b参数表示创建并切换，相当于如下2条命令

git branch dev

git checkout dev

git branch查看分支，当前分支前面会添加一个星号

在dev分支改变文件后，现在dev分支工作已完成，现在我们切换到主分支master上，我们可以把dev分支上的内容合并到分支master上了，可以在master分支上，使用如下命令 git merge dev 

git merge命令用于合并指定分支到当前分支上

查看分支：git branch

创建分支：git branch name

切换分支：git checkout name

创建+切换分支：git checkout –b name

合并某分支到当前分支：git merge name

删除分支：git branch –d name

分支策略：首先master主分支应该是非常稳定的，也就是用来发布新版本，一般情况下不允许在上面干活，干活一般情况下在新建的dev分支上干活，干完后，比如上要发布，或者说dev分支代码稳定后可以合并到主分支master上来。

# 多人协作

## 分支推送

推送分支就是把该分支上所有本地提交到远程库中，推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上：
 
 使用命令 git push origin master
