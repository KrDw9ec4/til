---
title: Pandoc 使用模板文件
published: 2025-01-12T08:00:00
modified: 2025-07-15T14:54:00
tags:
  - pandoc
  - markdown
---

我自己写文档一般都是用 Typora 编辑 Markdown 文件的，要发给别人的时候就导出为 PDF 或者 Word 文件。

Typora 是调用 Pandoc CLI 来导出为 .docx 文件的，但默认的导出效果很差。

Pandoc 支持使用模板文件，优化 Markdown 转 .docx 导出效果。

推荐模板：`templates_标题不编号.docx`，样式适合日常使用。

从 [Achuan-2/pandoc_word_template](https://github.com/Achuan-2/pandoc_word_template) 下载模板，保存后在 Typora 导出设置中选择即可。

注：选个合适的位置保存模板文件，不要直接丢在「下载」文件夹。

## References

- [Achuan-2/pandoc_word_template](https://github.com/Achuan-2/pandoc_word_template)