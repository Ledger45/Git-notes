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
> git clone git@github.com:username/repo_name.git

创建SSH key:
> ssh-keygen -t rsa -C "youremail@example.com"

