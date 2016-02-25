#### Git提交流程
> 工作区 -> git add -> 暂存区 -> git commit -> 版本库 -> git push -> 远程仓库

# 基本操作

把目录变成git可管理的仓库:
> git init

把文件添加到stage:
> git add \<filename\>

把文件提交到本地仓库：
> git commit -m "some description"

查看状态：
> git status

查看文件变化内容:
> git diff \<filename\>

查看提交的各版本日志:
> git log

根据commit-id回退版本:
> git reset --hard \<commit-id\>

查看之前输入的命令（可以看到reset之后git log看不到的commit-id，方便reset）:
> git reflog

查看工作区和版本库最新版本的区别(HEAD代表最新版，HEAD^表示上一版本，HEAD^^类推):
> git diff HEAD -- \<filename\>

让文件回到最近一次commit 或者 add 时的状态:
> git checkout -- \<filename\>

将stage的修改撤销掉，放回工作区（比如git add一个修改后，可以先git reset HEAD readme.txt，然后git checkout -- readme.txt，一切恢复:+1:）:
> git reset HEAD \<filename\>

删除文件，接着commit:
> git rm \<filename\>

关联远程库:
> git remote add origin https://github.com/username/repo_name.git

第一次推送master分支的所有内容，之后就不用加-u:
> git push -u origin master

克隆一个仓库，一个是https一个是ssh:
> git clone https://github.com/username/repo_name.git
> 
> git clone git@github.com:username/repo_name.git

创建SSH key:
> ssh-keygen -t rsa -C "youremail@example.com"

# 分支操作

创建并切换到dev分支：
> git checkout -b dev
>
> 相当于
>
> git branch dev
>
> git checkout dev

列出当前分支:
> git branch

切换到某分支:
> git checkout \<branchname\>

将dev分支合并到当前分支:
> git merge dev

将dev分支合并到当前分支（删除分之后log还在）:
> git merge --no-ff -m "merge with no-ff" dev 

将dev分支删除:
> git branch -d dev

查看分支合并情况:
> git log --graph --pretty=oneline --abbrev-commit

保存工作现场:
> git stash

查看stash
> git stash list

恢复现场并删除stash( 有多个stash时git stash apply stash@{0} 指定stash ):
> git stash pop
>
> 相当于
>
> git stash apply
>
> git stash drop

强制删除dev分支（dev分支如果没有merge的话用-d删不掉）
> git branch -D dev

在本地创建和远程分支对应的分支:
>  git checkout -b branch-name origin/branch-name

建立本地分支于远程分支的关联:
> git branch --set-upstream branch-name origin/branch-name

远程抓取最新提交:
> git pull

查看远程库信息:
> git remote -v

# 标签操作

建立tag，tag是版本库的快照，就是指向某个commit的指针，类似分支，但是分支可以移动，tag不行
> git tag -a \<tag-name\> -m "some description" 

查看tag信息:
> git show \<tag-name\>

对指定的commit-id添加tag
> git tag \<tag-name\> \<commit-id\>

删除本地的tag
> git tag -d \<tag-name\>

删除远程的tag:
> git push origin :refs/tags/\<tag-name\>

将tag推送到远端:
> git push origin \<tag-name\>

一次性推送所有tags:
> git push origin --tags

# 自定义Git

将命令alias为lg（方便啊~）
> git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

取消alias:
> git config --global unset alias.lg

让git显示颜色:
> git config --global color.ui true 










