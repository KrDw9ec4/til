---
title: 使用 Hugo 搭建 TIL 网站
published: 2025-07-13T01:22:00
modified: 2025-07-13T02:32:15
tags:
  - til
  - hugo
  - website
---

# 使用 Hugo 搭建 TIL 网站

今天使用 [Hugo](https://gohugo.io/) 框架和 [Hugo ʕ•ᴥ•ʔ Bear Blog](https://github.com/janraasch/hugo-bearblog/) 主题，搭建了一个 Today I Learned 网站，并通过 GitHub Workflow 实现自动化提交流程。

- TIL 笔记存放在 [KrDw9ec4/til](https://github.com/KrDw9ec4/til)。
- 网站源码放在 [KrDw9ec4/k1rin.com](https://github.com/KrDw9ec4/k1rin.com)。

其中关键的几点：

- 参考“References”中的链接，跑起来一个示例站点和自动部署工作流。

- 理解 Hugo 项目结构，更改站点配置文件 `Hugo.yaml`。

- 使用 `git submodule` 将 TIL 笔记仓库作为子模块导入，并在 workflow 中添加以下 Job：
  ```yaml
  - name: Update specific submodule
    run: |
      git submodule update --remote content/til
  ```
- 在 TIL 笔记仓库添加 Workflow，实现笔记更新时触发网站仓库重新部署。（Refer [1](https://github.com/peter-evans/repository-dispatch), [2](https://github.com/KrDw9ec4/k1rin.com/commit/f7c8b131e247e96d7ae67786946f975422178e5b)）

另外，我发现 Hugo 的项目结构设计的很优秀，之后可以考虑把博客文章也搬过来。

## References

- [Hugo Docs - Quick start](https://gohugo.io/getting-started/quick-start/)
- [Hugo Docs - Host on GitHub Pages](https://gohugo.io/host-and-deploy/host-on-github-pages/)
- [Hugo ʕ•ᴥ•ʔ Bear Blog](https://github.com/janraasch/hugo-bearblog/)
- [peter-evans/repository-dispatch](https://github.com/peter-evans/repository-dispatch)
