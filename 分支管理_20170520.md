> **分支管理**

![平行宇宙.png](http://upload-images.jianshu.io/upload_images/4712888-32d0350555760480.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

廖老师的这个比喻太棒了，分支类似平行宇宙！
目前工作在用 SVN，昨天天气热，机房直接歇菜了，代码提交不了，也更新不了，唉。。。。。。
知道 SVN 有分支功能，但一直没用，看来 git 的分支功能很强大啊，创建快，切换快。
使用分支是非常好的，你开发一个功能可能要好几天，没开发完提交上去，肯定会影响其他人，等着来找你吧。不提交，如果电脑挂了，代码没了，就找不回来了。所以创建一个自己的分支，在上面开发提交，开发完成，再把分支进行合并，这样很好的解决了问题。

> **创建与合并分支**

![分支.png](http://upload-images.jianshu.io/upload_images/4712888-c151f2f9624f01af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
说到分支得知道一些原理，指针的使用。
master 是主分支指针，指向 commit
我们可以创建分支指针，例如 dev，同样道理它也是指向 commit
HEADER 指针指向当前分支，即可能指向 master 或者 dev 或者其它创建的分支指针，分支的操作就是指针的操作，所以很快。

> 因为创建、合并和删除分支非常快，所以 Git 鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在 master 分支上工作效果是一样的，但过程更安全。
> 查看分支：git branch
创建分支：git branch <name>
切换分支：git checkout <name>
创建+切换分支：git checkout -b <name>
合并某分支到当前分支：git merge <name>
删除分支：git branch -d <name>

**解决冲突**
平时最怕遇见冲突了，搞不好把别人代码搞没了，所以一般开发都会先更新一下，这样可以减小冲突的概率，使用 git 遇到冲突，直接查看冲突文件，处理后，再提交一次就 OK 了，git 本身的操作没什么难度，关键在于文件冲突的处理。

**分支策略**
既然 git 的分支很好用，我们应该再开发中如何正确使用呢？
master 分支是最稳定的，一般不在上面工作，我们在 dev 分支工作，到发布一个版本时，merge 到 master 分支，而我们都在自己的分支上工作，开发完功能后 merge 到 dev 分支。

![分支策略.png](http://upload-images.jianshu.io/upload_images/4712888-b9a179c8a11d5751.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

之前我们 merge 使用的 fast forward，merge 后 git log 看不到 merge 情况，我们可以强制不使用 fast forward 方式，命令如下：
```git
git merge --no-ff -m "xxx"  <branch name>
```
**bug分支**
如果我们遵循上面的分支策略，当有 bug 需要修复时，我们可以切换到 dev 分支，由于我们不在 dev 分支开发，因此这时不涉及现场的保存问题。
如果我们是在 dev 分支直接开发的，那么就需要处理一下现场，即哪些在开发中的功能，由于没开发完所以不能直接提交，那怎么办呢？
使用 stash，用法如下：
```git
git stash #保存现场
git stash pop #恢复现场
```
**Feature分支**
开发一个新功能，最好新建一个 feature 分支，如果要删除未被合并的分支要使用的命令如下：
```git
git branch -D <branch name>
```
**多人协作**
```git
git remote #查看远程库信息
git remote -v #查看远程库信息详细
git push origin master #推送本地 master 分支
git checkout -b dev origin/dev #创建本地 dev 并关联远程 dev 分支
git branch --set-upstream branch-name origin/branch-name #建立本地分支与远程分支得关联
git pull #抓取远程分支
```
> 因此，多人协作的工作模式通常是这样：
首先，可以试图用 git push origin branch-name推送自己的修改；
如果推送失败，则因为远程分支比你的本地更新，需要先用 git pull 试图合并；
如果合并有冲突，则解决冲突，并在本地提交；
没有冲突或者解决掉冲突后，再用 git push origin branch-name推送就能成功！
如果 git pull 提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令 git branch --set-upstream branch-name origin/branch-name。
这就是多人协作的工作模式，一旦熟悉了，就非常简单。