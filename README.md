# git-guide
Git使用指南
#### 在GitHub上配置ssh秘钥，免登录  

#### Git基本操作
```
git clone 仓库地址   // 将代码克隆到本地
git branch -a  //查看本地及远程分支
git checkout dev   // 切换到指定分支（这里是dev分支）
git status // 查看仓库状态
git add  . or src // 将变更添加到暂存区(.表示当前路径下的全部文件，或指定目录src，或目录下具体文件src/filename)
git commit -m "comment info"  // 将暂存区文件变更提交到本地仓库
git pull origin main    // 同步远程分支到本地
git push origin
```

#### 创建新仓库的方式:  
- 命令行方式新建
```
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin 你的github空仓库地址
git push -u origin main
```  
- 基于已存在的本地仓库
```
git remote add origin 你的github空仓库地址
git branch -M main  
git push -u origin main
```
git push -u参数说明:  

将本地的main分支推送到origin主机，同时指定origin为默认主机，后面就可以不加任何参数使用git push了.
不带任何参数的git push，默认只推送当前分支到远程仓库，这种方式叫simple模式.
另外一种是matching，这种模式下讲本地所有对应分支推送到远程仓库。git2.0以后默认simple模式，可通过git config 设置：  
```
$ git config --global push.default matching/simple   // 二选一
```
#### 修改远程仓库地址
- 直接修改
```
git remote -v    // 查看远程仓库名
git remote set-url 远程仓库别名  新的远程仓库地址
```
- 先删除再修改
```
git remote rm 当前仓库别名
git add remote 给定仓库别名 新指定的仓库地址
```

#### 修改分支名  
```
git branch -m/M 新分支名
```
