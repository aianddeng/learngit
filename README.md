# GIT/GITHUB/GITEE #

***

## git 配置 ##

### 初始化 ###
> $ git config --global user.name/user.email 'xxx'
> $ git config --list/-l

### 创建仓库 ###
> $ git init

***

## 暂存区 ##

### 添加暂存 ###
> $ git add xxx

### 暂存区删除文件(工作区删除后操作,或执行add亦可) ###
> $ git rm xxx

### 提交暂存(描述) ###
> $ git commit -m 'xxx' 

***

## 查看状态 ##
> $ git status

### 查看不同,
```
1.工作区和暂存区 (2.暂存区-仓库) (3.工作区-仓库)  {后面跟文件名查看具体不同}
```
> $ git diff (--cached == --staged) (HEAD => HEAD^) xxx.file
```
4.查看分支不同，--stat只提供文件名。5.^表示查看b1有而b2没有的提交
```
> $ git diff branch branch2 (--stat) xxx.file
> $ git log branch ^branch2 (..)

***

## 撤销 ##

### 撤销工作区修改,恢复暂存区或仓库分支 ###
> $ git checkout -- xxx
> $ git restore xxx.file/.

### 撤销add操作(可与上一步结合 ###
> $ git reset HEAD xxx
> $ git restore --staged xxx.file/.

### 版本回退多个/指定 ###
> $ git reset --hard HEAD^(~2)/xxx

### 查看日志/命令历史(简述) (分支合并图) ###
> $ git log/reflog (--pretty=oneline) (--graph)

***

## 远程 ##

### 查看远程信息 ###
> $ git remote -v

### 添加远程仓库 ###
> $ git remote add origin xxx

### 修改远程仓库 ###
> $ git remote set-url origin xxx

### 删除远程仓库 ###
> $ git remote rm origin

### 推送到仓库(-u关联远程仓库,第一次需要加) ###
> $ git push (-u origin master)

### 合并到本地(多人协作,存在修改) ###
> $ git pull

### 分支创建链接关系 ###
> $ git branch --set-upstream-to=origin/dev dev

### 下载到本地 ###
> $ git clone xxx

***

## 分支 ##

### 创建并切换分支(基于远程创建分支) ###
> $ git checkout -b dev (origin/dev)
> $ git switch -c dev (origin/dev)

### 创建分支(-d删除分支)(-D强制删除) ###
> $ git branch dev

### 切换分支 ###
> $ git checkout dev
> $ git switch dev 

### 查看当前分支(所有分支/远程分支/分支详情/本地分支与远程分支关系) ###
> $ git branch -a/-r/-v/-vv

### 合并分支(HEAD 指向创建的分支) ###
> $ git merge dev

### 不舍弃master,commit分支的内容 ###
> $ git merge --no-ff -m 'xxx' dev

***

## 标签 ##

### 查看所有标签 ###
> $ git tag

### 创建一个新标签 ###
> $ git tag v1.0

### 删除一个标签 ###
> $ git tag -d v1.0

### 创建带描述的标签 ###
> $ git tag -a {tag-name} -m {description} {commit-id}

### 给commit建标签 ###
> $ git tag {tag-name} {commit-id}

### 查看标签详情 ###
> $ git show {tag-name}

### 提交单个标签到远程 ###
> $ git push origin {tagName}

### 提交所有标签到远程 ###
> $ git push origin -tags

***

## 储存区 ##

### 储存工作区(修复主分支bug后继续当前分支开发) ###
> $ git stash

### 查看储存区 ###
> $ git stash list

### 恢复工作区并删除储存 ###
> $ git stash pop

### 恢复工作区不删除储存 ###
> $ git stash apply

### 删除储存 ###
> $ git stash drop

***

## 变基 ##

### 打补丁 ###
> $ git rebase

***

## 忽略文件 ##

### 强制上传 ###
> $ git add -f xxx

### 查看问题 ###
> $ git check-ignore -v xxx

***

## 更多配置 ##

### 简写 ###
> $ git config --global alias.xx xxx

### 查看配置(当前) ###
> $ git config --global(local) --list
