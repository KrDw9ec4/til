---
title: 配置 Jupyter 开发环境（VS Code）
published: 2025-06-18T08:00:00
modified: 2025-07-13T23:08:14
tags:
  - vscode
  - jupyter
  - python
  - uv
  - ruff
---

1\. 创建并打开项目：

```shell
# 使用 uv 创建项目
uv init <project>
# 使用 VS Code 打开项目文件夹
code <project>
```

2\. 安装必要的 VS Code 扩展：

```json
// .vscode/extensions.json
{
    "recommendations": [
        "ms-toolsai.jupyter",
        "charliermarsh.ruff",
    ]
}
```

3\. 安装必要的 Python 包：

```shell
# cd <project>
uv add --dev ipykernel
uv add numpy pandas
# ...
```

4\. 配置 VS Code 使用 Ruff 对 Jupyter 文件格式化：

```json
// .vscode/settings.json
{
    "[python]": {
        "editor.formatOnSave": true, // 保存 Python 代码时自动格式化代码
        "editor.codeActionsOnSave": {
            "source.fixAll": "explicit",
            "source.organizeImports": "explicit",
        },
        "editor.defaultFormatter": "charliermarsh.ruff", // 指定代码格式化工具为 Ruff
    },
    "notebook.formatOnSave.enabled": true, // 保存 Notebook 文件时自动格式化代码
    "notebook.codeActionsOnSave": {
        "notebook.source.fixAll": "explicit",
        "notebook.source.organizeImports": "explicit",
    },
}
```

可以放在 `<project>/.vscode/settings.json`，只对当前项目有效；或者直接用作全局设置。

5\. 创建 `.ipynb` 文件时内核选择当前项目的虚拟环境。

## References

- [Using Jupyter from VS Code](https://docs.astral.sh/uv/guides/integration/jupyter/#using-jupyter-from-vs-code)
- [使用 uv + Ruff 设置您的 Python & VSCode & Notebook 环境！](https://qiita.com/dorimiamn/items/846fcc93e17dfea26d7d)