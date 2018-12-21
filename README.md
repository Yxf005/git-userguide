# git-guide
### TOC
- <a href="#安装">安装</a>
- <a href="#创建版本库">创建版本库</a>
- <a href="#状态与添加提交">状态与添加提交</a>
- <a href="#提交记录">提交记录</a>
- <a href="#版本回退">版本回退</a>
- <a href="#更新与发布">更新与发布</a>
- <a href="#分支与标记">分支与标记</a>

### 安装
---
- linux

```shell
yum -y install git
```
- macosx

```shell
brew install git
```

- windows

    下载二进制安装程序. [地址](https://pan.baidu.com/s/1kU5OCOB#list/path=%2Fpub%2Fgit)

  
  > 安装后 运行命令 `git` 查看
  
 :arrow_up: <a href="#toc">回到目录</a> 
  
###  创建版本库
- 创建新的版本库

```shell

git init

```

- 克隆已有的版本库

```shell

git clone ssh://user@xx.com/xxx.git

```

:arrow_up: <a href="#toc">回到目录</a>

### 状态与添加提交

- 查看当前版本库文件状态

```shell
git status
```

- 添加本地文件

```shell
git add tmp.txt
```
- 添加当前文件夹下文件

```shell
git add .
```

 > `add` 只是将文件变化提交到 暂存区

- 提交变化

```shell
git commit -m <message>
```
> `commit` 只提交暂存区(stage)内的文件变化

- 查看变化

```shell
git diff HEAD --<file>

git diff
```
:arrow_up: <a href="#toc">回到目录</a>

### 提交记录

- 查看所有提交记录

```shell
git log
```

- 查看某个文件的提交记录

```shell
git log -p <file>
```

- “追责”某个文件

```shell
git blame <file>
```
:arrow_up: <a href="#toc">回到目录</a>

### 版本回退

- 回退到上一版本 丢弃工作区的修改

```shell
git reset --hard HEAD
```

- 回退到某个指定版本

```shell
git reset --hard <commit id>
```
> commit id 可通过 `git log` 进行查看

- 回退后，重返较近的版本

```shell
git reflog 
git reset <commit id>
```

- 撤销修改

```shell
git checkout HEAD <file>
```

> 用命令 `git reset HEAD <file>` 可以把暂存区的修改撤销掉（unstage），重新放回工作区

- 丢弃工作区的修改

```shell
git checkout -- <file>
```

- 恢复某次提交

```shell
git revert <commit id>
```
:arrow_up: <a href="#toc">回到目录</a>

### 更新与发布

- 拉取最新修改到本地版本库

```shell
git pull <remote> <branch>
```

- 把本地提交内容推送到远程库

```shell
git push <remote> <branch>
```

> eg. `git push origin master`

:arrow_up: <a href="#toc">回到目录</a>

### 分支与标记

- 列出所有的分支

```shell
git branch -av
```

- 将工作区切换到某个分支

```shell
git checkout <branch>
```

- 切换新分支

```shell
git checkout -b <new_branch>
```

- 创建标记

```shell
git tag <tag_name>
```
> 命令 `git tag <tagname>` 用于新建一个标签，默认为 HEAD，也可以指定一个 commit id

- 查看所有的标记

```shell
git tag
```

- 删除标记

```shell
git tag -d <tag_name>
```
 :arrow_up: <a href="#toc">回到目录</a>

