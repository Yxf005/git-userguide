---
title: git 使用规范
date: 2019-04-03
version: 1.0
copyright: https://github.com/parselife
---

## git 使用规范


使用 `git` 进行代码开发，一般遵循以下流程：

```
主分支 ---> 新建 功能/修复/文档/... 分支 ---> merge request ---> 主分支
```
---
### 1. 新建分支

```shell
# 先切换到 master 分支，更新到最新版本，确保你的新分支是基于最新版本的master
git checkout master
# 在 master 分支上基本上只有一个操作 git pull
git pull
# 创建分支 git checkout 命令是切换分支，加上参数 -b 表示如果分支不存在，就创建，且立即切换到新创建的分支
git checkout -b jack/task-01
```

**分支命名规范**

分支名使用 `开发者/类型-目的` 的命名规则，其中 `类型` 可取值：

- fix: 修复bug. 后面 `目的` 应当指明 bug 编号 或 描述，如 `jack/fix-11`、`jack/fix-login-error`
- feat: 功能开发. 后面 `目的` 应当指明 需求编号 或 功能描述 如 `jack/feat-22` 、`jack/feat-add-login-validate`
- task: 禅道任务开发. 后面 `目的` 应当指明 任务编号 或 任务描述 如 `jack/task-33`、`jack/task-modify-login-logic`
- doc: 文档工作. 后面 `目的` 应当指明 文档名称 或 描述 如 `jack/doc-README`、`jack/doc-add-readme`

> 注：分支的开发者尽量是同一个人，个人分支在开发结束后，尽快提交 merge request.

---
### 2. 分支开发

```shell
# 添加工作区改变的文件到暂存区，尽量git add file1 file2
git add *
# 查看当前工作区的状态
git status
# 把暂存区内容放入版本库,加上 verbose 参数的话会对变化比较且显示
git commit --verbose
```
---
### 3. 提交备注信息
> git commit 的备注信息非常重要，尽量为有意义的信息。、

- 提交格式

```
# 类型： 主题  信息
<type>: <title>  <info>
```
**type** 

用于说明提交的类别, 可取值:
  - feat: 新功能
  - fix: 修补 bug
  - doc: 文档
  - style: 格式 代指不影响代码运行的改动
  - refactor: 重构，既不新增功能，也不是修复
  - test: 增加/修改 测试
  - revert: 撤销之前的提交

**title**

标题用于表示 需求编号\任务编号\bug编号\新功能名称\文档名称 等
如：

```
fix: bug-12  login error
feat: login-validate 
feat: task-34  add echarts
doc: ReadMe  update part 2
style: add lambda function 
```

**info**

信息用于描述详细信息.

---
### 4. 与远端同步

```shell
# 拉取远端仓库所有变更内容到本地仓库
# 注意和 git fetch origin 区别, fetch 不自动做合并
git pull origin
```
---
### 5. 推送到远端

```shell 
git push -u origin jack/feat-22 
```

### 6. 请求代码合并 merge request