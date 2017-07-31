### 问题：
已经添加了 SSH key，但是 push 的时候，需要输入，用户名和密码  
### 原因：
```git
git remote add origin https://github.com/zmdstr/learning_javascript.git
```
如上图，在添加远程仓库时，使用了 https 协议  
### 解决办法：
```git
 git remote rm origin
 git remote add origin git@github.com:zmdstr/learning_javascript.git
```
如上图，移除之前的远程仓库的添加，然后重新添加远程仓库，注意使用 SSH 协议