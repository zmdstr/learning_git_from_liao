- **自定义git**
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
git config --global alias.pom "push origin master"
```
![图片.png](http://upload-images.jianshu.io/upload_images/4712888-d801cf41e46bbd5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)