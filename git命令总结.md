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