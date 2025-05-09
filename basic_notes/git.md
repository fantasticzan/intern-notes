# Git命令

### 1. 配置与初始化

```bash
# 设置全局用户名和邮箱（所有仓库生效）
git config --global user.name "YourName"     # 配置提交者名称
git config --global user.email "your@email.com"  # 配置提交者邮箱

# 初始化本地仓库
git init               # 当前目录创建新仓库
git init project-dir  # 指定目录创建仓库

# 克隆远程仓库
git clone https://github.com/user/repo.git  # 克隆 HTTPS 协议仓库
git clone git@github.com:user/repo.git     # 克隆 SSH 协议仓库
```

### 2. 文件跟踪与提交

```bash
# 查看仓库状态（显示修改/未跟踪文件）
git status          # 显示工作区/暂存区状态

# 添加文件到暂存区
git add file.txt    # 添加单个文件
git add .           # 添加所有修改和新文件
git add *.js        # 通配符添加所有 .js 文件

# 提交到本地仓库
git commit -m "修复登录功能"  # 提交暂存区内容
git commit --amend          # 修改最近一次提交（如修复提交信息）
```

### 3. 分支操作

```bash
# 创建/切换分支
git branch feature-login   # 创建新分支
git switch feature-login   # 切换到分支（推荐新语法）
git switch -c new-feature  # 创建并切换到新分支

# 合并分支
git merge feature-login    # 合并分支到当前分支

# 删除分支
git branch -d feature-login  # 删除已合并的分支
git branch -D temp-branch   # 强制删除未合并的分支
```

### 4. 远程仓库操作

```bash
# 关联远程仓库
git remote add origin https://github.com/user/repo.git  # 添加远程仓库别名

# 推送本地分支到远程
git push origin main          # 推送main分支
git push -u origin main       # 首次推送并关联远程分支

# 拉取远程更新
git pull origin main         # 拉取并合并远程分支
git fetch origin            # 仅获取远程更新（不自动合并）

# 合并提交
git rebase -i HEAD~3        # 修改最近三次提交
```

### 5. 撤销与回退

```bash
# 撤销工作区修改
git restore file.txt       # 恢复文件到最近提交状态（Git 2.23+）
git checkout -- file.txt  # 旧版本实现相同功能

# 取消暂存区文件
git restore --staged file.txt  # 移出暂存区但保留修改（Git 2.23+）
git reset HEAD file.txt       # 旧版本语法

# 回退到指定提交
git reset --hard a1b2c3d  # 彻底丢弃后续修改
git revert a1b2c3d        # 安全撤销某次提交（生成新记录）
```

### 6. 查看历史与差异

```bash
# 查看提交历史
git log              # 完整提交记录
git log --oneline   # 简洁模式
git log --graph     # 图形化分支合并历史

# 查看文件差异
git diff            # 比较工作区与暂存区
git diff --staged   # 比较暂存区与最新提交
```

### 7. 其他实用操作

```bash
# 临时保存未完成修改
git stash         # 保存当前工作区
git stash pop     # 恢复最近保存的内容

# 清理未跟踪文件
git clean -fd     # 强制删除未跟踪文件和目录

# 标签管理
git tag -a v1.0 -m "正式版本1.0"  # 创建附注标签
git push origin --tags          # 推送所有标签到远程

# 远端更新了，但本地feature分支还在修改，怎么同步
git checkout master     # 切换master分支
git pull origin master  # 拉取更新

git checkout feature     # 切换feature分支
git rebase master        # 切换feature分支

git add <冲突文件>
git rebase --continue
```






### GitHub 常用术语中英对照表

| 英文术语          | 中文翻译            | 说明/用途                                      |
| ----------------- | ------------------- | ---------------------------------------------- |
| Repository        | 仓库 / 项目         | 代码项目的容器，每个项目一个仓库。             |
| Clone             | 克隆                | 把远程仓库复制到本地。                         |
| Fork              | 派生 / 复制一份仓库 | 通常用于开源项目协作，复制他人仓库到自己账户。 |
| Pull Request (PR) | 拉取请求 / 合并请求 | 提交代码更改请求，用于协作开发。               |
| Issue             | 问题 / 工单         | 用来追踪 bug、建议、任务等。                   |
| Commit            | 提交                | 一次代码保存记录，类似“存档”。                 |
| Branch            | 分支                | 代码的不同版本/实验路径。                      |
| Merge             | 合并                | 把某个分支的代码合并进另一个分支。             |
| Main / Master     | 主分支              | 项目的主要分支，默认是 main。                  |
| README.md         | 项目说明文档        | 仓库主页展示的说明，支持 Markdown。            |
| Push              | 推送（提交到远程）  | 把本地的 commit 推到 GitHub。                  |
| Pull              | 拉取（从远程获取）  | 把 GitHub 上的新代码拉到本地。                 |
| Actions           | 自动化操作 / 工作流 | 比如自动测试、部署等（CI/CD）。                |
| Stars             | 收藏 / 点赞         | 给项目点赞，相当于“关注”。                     |
| Watch             | 关注仓库            | 接收项目的更新通知。                           |
| Forked from       | 派生自（某项目）    | 说明该项目是从哪个仓库 Fork 来的。             |




