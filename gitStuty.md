#git学习笔记
**[网站来源](http://www.css88.com/archives/5361)**

* Git是目前世界上最先进的分布式版本控制系统。
* Git没有中央服务器的，每个人的电脑就是一个完整的版本库，这样，工作的时候就不需要联网了，因为版本都是在自己的电脑上。既然每个人的电脑都有一个完整的版本库，那多个人如何协作呢？比如说自己在电脑上改了文件A，其他人也在电脑上改了文件A，这时，你们两之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。

## Git Bash命令行小结
* cd e：  进e盘 （命令行是 e：）  
* cd www  进文件夹

## git初始设置
*$ git config --global user.name "yezi153"
*$ git config --global user.email "1435443048@qq.com"
*git config  –global 参数，有了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然你也可以对某个仓库指定的不同的用户名和邮箱。


## 一、安装Git Bash

一：如何操作:
1.创建一个版本库也非常简单，如下我是E盘 –> www下 目录下新建一个testgit版本库($pwd 命令是用于显示当前的目录);
2.通过命令$git init 把这个目录变成git可以管理的仓库,  这时候你当前testgit目录下会多了一个.git的目录，这个目录是Git来跟踪管理版本的，没事千万不要手动乱改这个目录里面的文件，否则，会把git仓库给破坏了。
如何本地提交文件：
第一步：使用命令 git add readme.txt添加到暂存区里面去;($git add readme.txt)
第二步：用命令 git commit告诉Git，把文件提交到仓库;($git commit -m 'readme.txt')
现在我们已经提交了一个readme.txt文件了，我们下面可以通过命令git status来查看是否还有文件未提交;($git status)
如果命令告诉我们 readme.txt文件已被修改，但是未被提交的修改，接下来我想看下readme.txt文件到底改了什么内容，如何查看呢？可以使用如下命令：
$git diff readme.txt

二：版本回退

git log                   查看下历史记录
git log –pretty=oneline    嫌上面显示的信息太多的话
git reset  –hard HEAD^     回退到上一个版本
git reset  –hard HEAD^^    回退到上上一个版本
git reset  –hard HEAD~100  回退到前100个版本
git reflog                 获取到版本号
git reset  –hard 6fcfc89    通过版本号回退

工作区：就是你在电脑上看到的目录，比如目录下testgit里的文件(.git隐藏目录版本库除外)。或者以后需要再新建的目录文件等等都属于工作区范畴。
版本库(Repository)：工作区有一个隐藏目录.git,这个不属于工作区，这是版本库。其中版本库里面存了很多东西，其中最重要的就是stage(暂存区)，还有Git为我们自动创建了第一个分支master,以及指向master的一个指针HEAD。

我们前面说过使用Git提交文件到版本库有两步：
  第一步：是使用 git add 把文件添加进去，实际上就是把文件添加到暂存区。
  第二步：使用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支上。

Git撤销修改和删除文件操作
cat readme.txt   查看文件内容
git checkout --readme.txt   撤销readme.txt修改

删除文件
一般情况下，可以直接在文件目录中把文件删了，或者使用如上rm命令：rm b.txt ，如果我想彻底从版本库中删掉了此文件的话，可以再执行commit命令提交掉



git远程库
添加了git远程库后只要本地作了提交，就可以通过如下命令：
git push origin master
把本地master分支的最新修改推送到github上了。

克隆命令  git clone https://github.com/tugenhua0707/testgit2

git checkout -b dev   创建并切换分支向，相当于如下2条命令
git branch dev         
git checkout dev

总结创建与合并分支命令如下：

查看分支：git branch

创建分支：git branch name

切换分支：git checkout name

创建+切换分支：git checkout –b name

合并某分支到当前分支：git merge name

删除分支：git branch –d name

如果我想查看分支合并的情况的话，需要使用命令 git log.命令行

 通常合并分支时，git一般使用”Fast forward”模式，在这种模式下，删除分支后，会丢掉分支信息，现在我们来使用带参数 –no-ff来禁用”Fast forward”模式。

分支策略：首先master主分支应该是非常稳定的，也就是用来发布新版本，一般情况下不允许在上面干活，干活一般情况下在新建的dev分支上干活，干完后，比如上要发布，或者说dev分支代码稳定后可以合并到主分支master上来。



Git基本常用命令如下：

   mkdir：         XX (创建一个空目录 XX指目录名)

   pwd：          显示当前目录的路径。

   git init          把当前的目录变成可以管理的git仓库，生成隐藏.git文件。

   git add XX       把xx文件添加到暂存区去。

   git commit –m “XX”  提交文件 –m 后面的是注释。

   git status        查看仓库状态

   git diff  XX      查看XX文件修改了那些内容

   git log          查看历史记录

   git reset  –hard HEAD^ 或者 git reset  –hard HEAD~ 回退到上一个版本

                        (如果想回退到100个版本，使用git reset –hard HEAD~100 )

   cat XX         查看XX文件内容

   git reflog       查看历史记录的版本号id

   git checkout  --XX  把XX文件在工作区的修改全部撤销。

   git rm XX          删除XX文件

   git remote add origin https://github.com/tugenhua0707/testgit 关联一个远程库

   git push –u(第一次要用-u 以后不需要) origin master 把当前master分支推送到远程库

   git clone https://github.com/tugenhua0707/testgit  从远程库中克隆

   git checkout –b dev  创建dev分支 并切换到dev分支上

   git branch  查看当前所有的分支

   git checkout master 切换回master分支

   git merge dev    在当前的分支上合并dev分支

   git branch –d dev 删除dev分支

   git branch name  创建分支

   git stash 把当前的工作隐藏起来 等以后恢复现场后继续工作

   git stash list 查看所有被隐藏的文件列表

   git stash apply 恢复被隐藏的文件，但是内容不删除

   git stash drop 删除文件

   git stash pop 恢复文件的同时 也删除文件

   git remote 查看远程库的信息

   git remote –v 查看远程库的详细信息

   git push origin master  Git会把master分支推送到远程库对应的远程分支上