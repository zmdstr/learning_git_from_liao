windows git 直接去官网就行，地址如下：
https://git-scm.com
安装后，要进行配置：
```java
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

>注意 git config 命令的 --global 参数，用了这个参数，表示你这台机器上所有的 Git 仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和 Email 地址。

在项目根目录下进行单独配置
```java
git config user.name "Your Name"
git config user.email "email@xx.com"
```
git config --list 查看当前配置, 在当前项目下面查看的配置是全局配置+当前项目的配置, 使用的时候会优先使用当前项目的配置