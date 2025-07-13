---
title: 使用 uv 的工作流程
published: 2025-06-01T08:00:00
modified: 2025-07-13T23:13:21
tags:
  - python
  - uv
---

新建项目：

```shell
uv init <project>
cd <project>
git add .
git commit -m "Initial commit"
```

进行编辑和提交修改：

```shell
# uv add requests
# ...
git add [...]
git commit -m "[...]"
```

上传到远程仓库：

```shell
git remote add origin git@github.com:<USERNAME>/<REPO>.git
git branch -M main
git push -u origin main
```

其他机器拉取后：

```shell
git clone https://github.com/<USERNAME>/<REPO>.git
cd <REPO>
# 同步环境
uv sync
```