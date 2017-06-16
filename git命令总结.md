- 配置全局用户及邮箱
```java
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```
- 配置当前仓库用户及邮箱
```java
git config user.name "Your Name"
git config user.email "email@xx.com"
```
- 查看配置文件内容
```java
git config --list
```
- 初始化版本库
```java
git init  
```
- 把文件放到 git 仓库
```java
git add
```
- 把文件提交到 git 仓库
```java
git commit -m "xxx"
```
- 提交本地工作目录下所有修改，而不需要先 git add,相当于：git add 和 git commit
```java
git commit -am"message"
```
- 查看当前仓库状态
```java
git status
```
- 查看文件修改
```java
git diff <file>
```
> 评论区
```gitbash
git diff    #是工作区(work dict)和暂存区(stage)的比较
git diff --cached    #是暂存区(stage)和分支(master)的比较
git diff HEAD  #查看工作区和版本库里面最新版本的区别
```
- 查看提交日志
git log
git log --pretty=oneline
- 版本回退到上一个版本
```java
git reset --hard HEAD^
git reset --hard 3628164
```
- 查看命令日志
```java
git reflog
```
- 丢弃工作区修改
```git
git checkout -- file
```
- 撤销暂存区修改
```git
git reset HEAD file
```
- 删除暂存区文件
```git
git rm <file>
git commit -m "xxxx"
```
- 从暂存区恢复删除文件
```git
git checkout --<file>
```
- 关联远程仓库
```git
git remote add origin git@server-name:path/repo-name.git
```
- 首次 push 到远程仓库
```git
 git push -u origin master 
```
- 非首次推送到远程仓库
```git
git push origin master 
```
- 从远程仓库克隆
```git
git clone git@server-name:path/repo-name.git
```
- 分支管理
```git
查看分支：git branch
创建分支：git branch <name>
切换分支：git checkout <name>
创建+切换分支：git checkout -b <name>
合并某分支到当前分支：git merge <name>
删除分支：git branch -d <name>
```
- 禁止使用 fast forward merge 方式
```git
git merge --no-ff -m "xxx"  <branch name>
```
- 隐藏现场及回复现场
```git
git stash #保存现场
git stash pop #恢复现场
```
- 强制删除未合并分支
```git
git branch -D <branch name>
```
- 多人协作
```git
git remote #查看远程库信息
git remote -v #查看远程库信息详细
git push origin master #推送本地 master 分支
git checkout -b dev origin/dev #创建本地 dev 并关联远程 dev 分支
git branch --set-upstream branch-name origin/branch-name #建立本地分支与远程分支得关联
git pull #抓取远程分支
```
- 创建标签
```git
git tag <name>  #创建标签
git tag #查看所有标签
git tag v0.9 6224937 #对某一次 commit 打标签
git show <tagname> #查看标签信息
git tag -a v0.1 -m "version 0.1 released" 3628164 #创建有说明的标签
```
- 操作标签
```git
git tag -d v0.1 #删除标签
git push origin <tagname> #推送标签到远程
git push origin --tags #推送本地所有未推送到远程的标签
git push origin :refs/tags/<tagname> #删除远程标签
```
- 自定义git
```git
git config --global color.ui true #配置颜色开启
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.br branch
git config --global alias.unstage 'reset HEAD'
git config --global alias.last 'log -1'
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
git config --global core.quotepath false # 设置显示中文文件名
```