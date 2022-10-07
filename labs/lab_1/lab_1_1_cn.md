# 实验一: 实验课框架代码 wpfTest 概述

go to [English Version](lab_1_1.md)

## 1 浏览 wpfTest 的代码，熟悉框架结构

用如下命令下载代码
```batch
git clone https://gitee.com/principlewindows/wpfTest.git
```

### 1.1 打开下载的代码

- 切换文件夹视图与解决方案视图
- `Show All Files` 按钮及作用

### 1.2 git 与 Visual Studio

- 如何创建远程仓库，以 gitee 举例
- 如何生成 commit 及提交到远程仓库
    - 同步提交到 gitee 和 github 的方法参见 <https://gitee.com/principlewindows/gitMem>
- 如何设置 git 的外部 difftool 
    - 方法一：<https://www.git-scm.com/book/en/v2/Customizing-Git-Git-Configuration>
    \
    D:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer\vsDiffMerge.exe
    - 方法二：在 `Team Explorer` 中配置

### 1.3 在 VS 中比对两次提交文件差异的实验

1. 在 wpfTest 项目文件夹处打开 `PowerShell`
2. 查看 commits: `git reflog`
3. 比较差异：`git difftool fad55e6 95a8486`

## 2 熟悉 WPF 窗体应用程序创建流程

1. 在 Visual Studio 2022 Community 中创建一个 WPF 窗体应用程序
2. 添加基本控件如 button, label, textbox, listbox, dataGrid, combox 等常用控件
