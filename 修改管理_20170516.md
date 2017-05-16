*update 20170516*

> 为什么 Git 比其他版本控制系统设计得优秀，因为 Git 跟踪并管理的是修改，而非文件。
git commit 只负责把暂存区的修改提交了。
每次修改，如果不 add 到暂存区，那就不会加入到 commit 中。
主要注意下面三个命令
```gitbash
git diff    #是工作区(work dict)和暂存区(stage)的比较
git diff --cached    #是暂存区(stage)和分支(master)的比较
git diff HEAD  #查看工作区和版本库里面最新版本的区别
```