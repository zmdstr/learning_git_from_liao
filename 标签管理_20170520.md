**标签管理**
我们每次上线的版本都应该打一个标签，标签指向一个 commit，标签方便我们拿到某一次特殊的 commit
**创建标签**
```git
git tag <name>  #创建标签
git tag #查看所有标签
git tag v0.9 6224937 #对某一次 commit 打标签
git show <tagname> #查看标签信息
git tag -a v0.1 -m "version 0.1 released" 3628164 #创建有说明的标签
```
**操作标签**
```git
git tag -d v0.1 #删除标签
git push origin <tagname> #推送标签到远程
git push origin --tags #推送本地所有未推送到远程的标签
git push origin :refs/tags/<tagname> #删除远程标签
```