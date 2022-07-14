使用git提交时，要配置好邮箱，邮箱与github一致时，才是自己名下提交的。尤其是有配置全局用户和邮箱的时候，需要特别注意。

git checkout --orphan latest_branch 新建一个空白分支
git add -A  添加所有文件
git push -f origin master  强制推送到远程仓库
git branch -m master   将当前分支命名为master
git branch -D dev    强制删除所有分支，如果是dev


### 修改个人提交记录,包括作者，邮箱

1. 修改最后一次提交记录
···
git commit --amend   修改注释  
git commit --amend --author="{username} <{email}>"
···
此时进入vi界面，i进入编辑模式，修改后输入:wq保存退出  


2. 修改某几次提交记录  
先查看对应修改的commit ID  
···
git log --oneline  查看保护主要信息的提交log
···
然后使用git rebase命令  
···
git rebase -i {commitId}   修改该commitId之前的注释，不包含修改该commitId的信息
···
此时进入vi界面，将需要修改的项的pick改为edit模式，可以同时改多个。  
接下来，使用git commit --amend命令修改邮箱，注释和作者信息  
···
git commit --amend --author="{username} <{email}>"   修改邮箱，注释和作者信息
···
修改完成后，执行如下命令：
···
git rebase --continue
···
如果是修改多条记录，重复以上步骤，直到出现如下信息：  Successfully rebased and updated refs/heads/master.  
最后，将本地修改的内容push到远程仓库，注意多人协作时，需要考虑是否覆盖别人的代码
···
git push --force 远程仓库名 远程分支名
···
