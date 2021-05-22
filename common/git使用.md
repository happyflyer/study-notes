# git 使用

- [Git 教程 - 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/896043488029600)
- [Git 远程操作详解 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)

## 1. 全局配置

```bash
git config --global user.name "your_name"
```

```bash
git config --global user.email "your_email@example.com"
```

```bash
# 提交时转换为LF，检出时不转换（推荐配置）
git config --global core.autocrlf input
# 提交时转换为LF，检出时转换为CRLF
git config --global core.autocrlf true
# 提交检出均不转换
git config --global core.autocrlf false
```

```bash
# 拒绝提交包含混合换行符的文件（推荐配置）
git config --global core.safecrlf true
# 允许提交包含混合换行符的文件
git config --global core.safecrlf false
# 提交包含混合换行符的文件时给出警告
git config --global core.safecrlf warn
```

## 2. 日常使用

- 工作区
- 暂存区
- 版本库

```bash
# ssh
git clone git@github.com:github/gitignore.git
# https
git clone https://github.com/github/gitignore.git
```

```bash
git init
```

```bash
git add doc.txt
```

```bash
git commit -m "add doc.txt"
```

```bash
git status
```

```bash
git diff doc.txt
```

## 3. 日志和切换

```bash
git log
git log --pretty=oneline
# 分支图
git log --oneline --graph --decorate --all
```

```bash
# 命令历史
git reflog
```

```bash
# 回退到指定提交
git reset --hard commit_id
# 回退到上个版本
git reset --hard HEAD^
# 回退到前3次的提交
git reset --hard HEAD~3
```

## 4. 撤销和丢弃

### 4.1. 撤销暂存区的修改

```bash
git reset HEAD doc.txt
```

### 4.2. 丢弃工作区的修改

```bash
git checkout -- doc.txt
```

- `doc.txt` 自修改后还没有被放到暂存区，撤销修改就回到**和版本库一模一样的状态**。
- `doc.txt` 已经添加到暂存区后，又作了修改，撤销修改就回到**添加到暂存区后的状态**。

## 5. 删除和恢复

### 5.1. 删除工作区和版本库的文件

```bash
rm doc.txt
git rm doc.txt
git commit -m "del doc.txt"
```

### 5.2. 删除了工作区的文件后，从版本库恢复

```bash
rm doc.txt
git checkout -- doc.txt
```

## 6. 分支和标签

```bash
# 创建并切换分支
git checkout -b dev
# 切换分支
git checkout dev
```

```bash
git merge dev
```

```bash
git tag 0.1.0
git checkout 0.1.0
```

```bash
# 删除标签
git tag -d 0.1.0
git push origin :refs/tags/0.1.0
```

## 7. 关联远程仓库

- 本地仓库
- 远程仓库

```bash
ssh-keygen -t rsa -C "your_message"
```

将公钥 `~/.ssh/id_rsa.pub` 添加到 github/gitlab/gitee/.. 账户的 SSH 公钥。

```bash
ssh -T git@github.com
```

```bash
git remote
git remote -v
git remote add origin git@server_name:username/repo_name.git
git remote set-url origin git@server_name:username/repo_name.git
git remote rename origin github
```

## 8. 拉取和推送

### 8.1. 拉取

```bash
# git pull <远程主机名> <远程分支名>:<本地分支名>
git pull origin next:master
# pull = fetch + merge
git fetch origin dev:dev
```

### 8.2. 推送

```bash
# git push <远程主机名> <本地分支名>:<远程分支名>
git push origin master
# 首次推送分支
git push -u origin master
```

```bash
# 推送所有分支
git push origin --all
# 推送所有标签
git push origin --tags
```

```bash
# 删除远程分支
git push origin --delete dev
```

## 9. 子模块

- [git-submodule - 摸鱼划水](https://blog.justwe.site/post/git-submodule/)

```bash
git submodule add git@github.com:github/gitignore.git
```

```bash
git submodule update --init --recursive
```

```bash
# 删除子模块
git rm submodule_name
git submodule deinit submodule_name
```
