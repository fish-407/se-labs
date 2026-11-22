# 软件工程原理与实践 · 课程实验报告（LaTeX 源码）

中国海洋大学《软件工程原理与实践》课程实验报告源码汇总。
姓名：张中瑞　学号：24020007166

本项目由原先分散的多个实验仓库合并而来，每个实验一个子目录，内含 LaTeX 源码与图片资源。

## 目录

| 目录 | 实验内容 | 原仓库 | 日期 |
|---|---|---|---|
| `lab01_latex_git/` | LaTeX 与 Git 练习（文档类型、beamer、figure、git 常用操作） | fish-407/-Latex-and-git | 2025-08-29 |
| `lab02_shell_vim/` | Shell 与 Vim 练习（文件操作、权限、Vim 编辑命令） | fish-407/test2 | 2025-09-10 |
| `lab03_cli_python/` | 命令行环境与 Python（进程管理、tmux、ssh、Python 基础与图像处理） | fish-407/test3 | 2025-09-19 |
| `lab04_debug_pytorch/` | 调试与性能分析、元编程、PyTorch 编程（pdb、lsof、Wireshark、Makefile、pre-commit、GitHub Actions） | fish-407/test4 | 2025-09-23 |
| `lab05_ouc_beamer/` | beamer 演示文稿：中国海洋大学简介 | fish-407/lesson1--1- | — |

每个目录下的 `main.tex` 是该次实验的入口文件。

## 编译

文档使用 `ctexart` / `beamer` + `xeCJK`，**必须用 XeLaTeX 编译**（pdflatex 处理中文会失败）：

```bash
cd lab01_latex_git
xelatex main.tex
xelatex main.tex   # 第二次编译以生成目录和交叉引用
```

或用 latexmk：

```bash
latexmk -xelatex main.tex
```

如果本机没有安装 TeX 发行版，可直接把目录上传到 [Overleaf](https://www.overleaf.com/)（Compiler 选 XeLaTeX）编译。

## 说明

- 编译产生的 `.aux / .log / .out / .toc / .synctex.gz` 等中间文件已在 `.gitignore` 中排除。
- `lab05_ouc_beamer/main.tex` 中引用的图片文件名为 `R-C.jpg`（原文件写作 `R-c.jpg`，在 Windows 上不区分大小写可编译，在 Linux/macOS 上会报错，此处已统一为 `R-C.jpg`）。
- 若仓库中需要附带编译好的 PDF，取消 `.gitignore` 中对 `*.pdf` 的排除即可。
