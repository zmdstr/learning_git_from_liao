问题：  
直接修改了 git 仓库的文件名，由 pathon -> python，然后 add commit push，
发现 github 上出现了两个文件，一个 pathon，一个 python  
解决方法：  
```python
git rm pathon简介.md
git ci pathon简介.md -m 'delete'
git push origin master
```