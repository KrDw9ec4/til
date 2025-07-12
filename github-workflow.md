---
title: GitHub 工作流
published: 2025-07-11T12:55:00
modified: 
tags:
  - git
  - github
---

# GitHub 工作流

不要直接在 main 分支修改，每次都要新建一个 feat 分支，功能开发完全之后 Pull Request 到 main 分支（采用 squash and merge 的方式）。

这样可以确保 main 分支每一个提交都是可以正常运行的。

## 具体流程

### 1. 克隆到本地进行修改

```shell
git clone ...
cd ...
# 创建新分支进行修改
git switch -c feat-new-feature
# 开始进行修改
git diff [...] [...]
git add [...]
git commit -m [...]
# 将新分支上传到远程仓库
git push origin feat-new-feature
```

### 2. 与远程 main 分支同步

```shell
git switch main
git pull origin main
git switch feat-new-feature
# 进行 rebase 并手动处理冲突
git rebase main
git push -f origin feat-new-feature
```

### 3. Pull Request

前往 GitHub 进行 PR，使用 Squash and Merge 来合并 feat-new-feature 分支上的提交。

### 4. 本地收尾处理

```shell
# 删除本地的新分支
git branch -d feat-new-feature
# 拉取最新代码
git pull origin main
```

## References

- [码农高天 - 十分钟学会正确的github工作流，和开源作者们使用同一套流程](https://bilibili.com/video/BV19e4y1q7JJ/)
- [GitHub Docs - GitHub flow](https://docs.github.com/en/get-started/using-github/github-flow)
- [Learning Git Branching](https://learngitbranching.js.org/?locale=zh_CN)