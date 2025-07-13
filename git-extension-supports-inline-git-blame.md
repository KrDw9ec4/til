---
title: Git 扩展支持行内 Git Blame 显示，替代 Git Blame 扩展
published: 2025-07-11T11:44:00
modified: 2025-07-13T03:21:01
tags:
  - git
  - vscode
---

原先我一直使用 [Git Blame](https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame) 扩展来显示行内 git blame。

```json
{
  "gitblame.inlineMessageEnabled": true,
  "gitblame.inlineMessageFormat": " ${author.name}, ${time.ago} · ${commit.summary}",
}
```

现在发现新版的 Git 扩展已经支持 git blame 了，之后可以少装一个扩展。

```json
{
  "git.blame.editorDecoration.enabled": true,
  "git.blame.editorDecoration.template": "${authorName}, ${authorDateAgo} · ${subject}",
}
```

测试下来显示效果是差不多的。