---
title: 备份 GitHub 仓库
published: 2025-07-17T22:20:00
modified: 
tags:
  - github
  - backup
---

因为我开始使用 GitHub Issues 来追踪问题，所以需要定期备份以防万一。

simonw 在推荐 GitHub Issues 的同时，也推荐了他自己写的 github-to-sqlite 来备份，试了一下，感觉确实不错。

## 安装

使用 pip 安装

```shell
pip install github-to-sqlite
```

或者，使用 uv 安装：

```shell
uv tool install github-to-sqlite
```

## 使用

先去 https://github.com/settings/tokens 生成一个 token，授予相应的 Issues 和 Pull requests 等的读权限。

```shell
# 创建和打开保存备份文件的目录
mkdir github-to-sqlite
cd github-to-sqlite
```

```shell
# 添加 token
uvx github-to-sqlite auth
# 粘贴刚才生成的 token
```

```shell
# 备份 Issues
uvx github-to-sqlite issues github.db simonw/datasette
```

```shell
# 备份 Issue Comments
uvx github-to-sqlite issue-comments github.db simonw/datasette
```

## References

- https://k1rin.com/til/github-issues-for-notes/
- https://github.com/dogsheep/github-to-sqlite
- https://docs.astral.sh/uv/concepts/tools/
- https://docs.astral.sh/uv/guides/tools/