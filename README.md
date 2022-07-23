# git-guide
Git使用指南
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

#### 修改分支名  
```
git branch -m/M
```
