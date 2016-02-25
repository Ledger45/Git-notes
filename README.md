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

查看之前输入的命令（可以看到reset之后git log看不到的commit-id，方便reset）
> git reflog
