> 首先，Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，也就是最新的提交3628164...882e1e0（注意我的提交ID和你的肯定不一样），上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。
- 现在总结一下：
    HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
    穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
    要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

如果同时修改了多个文件，当版本回退时，所有文件都进行回退，这个和ide 中使用的 revert 不同，查找回退单个文件操作如下
- 将单个文件回退
参考地址：http://blog.csdn.net/b_h_l/article/details/17266849
```gitbash
$ git log readme.txt
$ git reset xxx readme.txt
$ git commit -m "revert"
$ git checkout readme.txt
$ git push origin master
```