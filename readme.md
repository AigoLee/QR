#git使用命令

#基本命令
##1. git init 
通过命令把这个目录变成git可以管理的仓库

##2. git push origin master
只要本地作了提交，就可以通过上面命令：
把本地master分支的最新修改推送到github上了，现在你就拥有了真正的分布式版本库了。

##3.git add readme.txt添加到暂存区里面去

##4. 用命令git commit告诉Git，把文件提交到仓库。

##5.通过命令git status来查看状态

#版本回退

##git log命令显示从最近到最远的显示日志，我们可以看到最近三次提交

##git reset --hard HEAD^ 那么如果要回退到上上个版本只需把HEAD^ 改成 HEAD^^ 以此类推

##我们可以通过版本号回退，使用命令方法如下：git reset --hard 版本号
##可以通过如下命令即可获取到版本号：git reflog

##git checkout -- file 可以丢弃工作区的修改
命令 git checkout --readme.txt 意思就是，把readme.txt文件在工作区做的修改全部撤销，这里有2种情况，如下：
1.readme.txt自动修改后，还没有放到暂存区，使用 撤销修改就回到和版本库一模一样的状态。
2.另外一种是readme.txt已经放入暂存区了，接着又作了修改，撤销修改就回到添加暂存区后的状态。

#删除文件

##rm filename
如果我想彻底从版本库中删掉了此文件的话，可以再执行commit命令 提交掉

只要没有commit之前，如果我想在版本库中恢复此文件如何操作呢？

可以使用如下命令 git checkout -- b.txtc


