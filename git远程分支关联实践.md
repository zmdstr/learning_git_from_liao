1.在本地创建和远程分支对应的分支，使用
	git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；

2.（已有同名分支）建立本地分支和远程分支的关联，使用
	git branch --set-upstream origin/branch-name  branch-name