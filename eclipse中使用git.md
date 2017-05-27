如果在命令行，你已经掌握了 git 的使用，那么在其他 ide 中，你一样可以轻松的使用 git ，只是需要熟悉一下菜单的位置而已。
我目前使用的是 STS ，相关操作与 eclipse 一样。
点击 window -> preferences -> Team 如下图可以看到 STS 已经内置了 git 。
![team.png](http://upload-images.jianshu.io/upload_images/4712888-7c3cddde622087e4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 将已有项目使用 git 进行版本控制
项目右键 Team -> Share Project... ->选择 git -> 配置 git 仓库 这时我们可以选择已有的 git 仓库或者新建 git 仓库 -> 点击 create 选择一个空的目录 -> 点击 finish 现在项目已经与 git 进行了关联，如图：

![git 关联.png](http://upload-images.jianshu.io/upload_images/4712888-7703bd9ced32324f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接下来，我们先进入 刚刚创建的 git 仓库，在 .git 同级目录下，创建一个 .gitignore 文件，我的文件内容如下：
```java

# Created by https://www.gitignore.io/api/eclipse
### Eclipse ###
target/
testLogs/
.metadata
bin/
tmp/
*.tmp
*.bak
*.swp
*~.nib
local.properties
.settings/
.loadpath
.recommenders
# External tool builders
.externalToolBuilders/
# Locally stored "Eclipse launch configurations"
*.launch
# PyDev specific (Python IDE for Eclipse)
*.pydevproject
# CDT-specific (C/C++ Development Tooling)
.cproject
# Java annotation processor (APT)
.factorypath
# PDT-specific (PHP Development Tools)
.buildpath
# sbteclipse plugin
.target
# Tern plugin
.tern-project
# TeXlipse plugin
.texlipse
# STS (Spring Tool Suite)
.springBeans
# Code Recommenders
.recommenders/
# Scala IDE specific (Scala & Java development for Eclipse)
.cache-main
.scala_dependencies
.worksheet
### Eclipse Patch ###
# Eclipse Core		
.project
# JDT-specific (Eclipse Java Development Tools)		
.classpath
# End of https://www.gitignore.io/api/eclipse
```
这样就可以排除我们不想被 git 管理的文件，放心提交了。
接下来回到 STS 在项目上右键选择 Team，git 的常规操作菜单都在这里，和命令行操作一样，add 后 commit ，这时就一切 OK 了，如图：

![提交完成.png](http://upload-images.jianshu.io/upload_images/4712888-0e144e6f45472759.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- push 到 github

![图片.png](http://upload-images.jianshu.io/upload_images/4712888-9f944b5e7d90683a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

直接在 URI 中填入 github 仓库地址，其它项目会自动补充，然后下一步即可。