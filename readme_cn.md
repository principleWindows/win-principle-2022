# Windows Principles and Its Applications

[English Version](readme.md)

**Please leve your comment, suggestion, question in the comment feedback or send me emails!**

武汉大学计算机学院课程:
* (2022-2023-1)-3350520011035-软工 《Windows原理与应用》

教学资源站点

“Windows Principle and Its Applications” is a course of teaching
general purpose windows 
programming knowledge to develop software system running on Windows 
platform, via different programming languages that supports 
various computer programming models such as object-oriented 
programming and generic programming. Its main purpose is to make 
writing good programs easier and more pleasant for the Windows 
platform programmer.

By learning this course, you will be training with up-to-date 
technology, including uwp, fluent design, c++/winRt, c#/winRt etc, 
to create stunning modern windows applications, using a suite of 
collaborative tools. These learning opportunities can help you 
get started quickly — from exploration to deep training.

Instructor: Professor Jicheng Hu \
主讲教师: 胡继承 教授


## <span id="index">目录</span>


0. [Introduction](#introduction)
1. [Visual Studio](#visual-studio)
2. [git, github and gitee](#git-github-and-gitee)
3. [WSL](#wsl)
4. [Course Lab](#course-lab)
5. [refs](#refs)
6. [Academic Integrity](#academic-integrity)
7. [How to contribute](#how-to-contribute)
8. [Preprint of Text](#preprint-of-text)


## 0 Introduction
slides and resource for the course "principle of windows and its applications"

### 0.1 course slides:

#### [1 Windows操作系统概述](slides/coursePPT/01Introduction2WindowsOS.pptx)

#### [2 程序进程与进程间通信](slides/coursePPT/02process.pptx)

#### [3 线程间通信与同步](slides/coursePPT/03thread.pptx)

#### [4 文件系统管理](slides/coursePPT/04fs.pptx)

#### [5 WINDOWS 注册表](slides/coursePPT/05registry.pptx)

#### [6 动态链接库](slides/coursePPT/06dll.pptx)

#### [7 COM](slides/coursePPT/07COM.pptx)

#### [8 消息与事件](slides/coursePPT/08msg_n_events.pptx)

### 0.2 instruction slides:

#### [0 课程介绍](slides/instruction/introduction.pptx)

#### [1 Windows操作系统概述](slides/instruction/principleWindows_1.pptx)

#### [2 程序进程与进程间通信](slides/instruction/principleWindows_2.pptx)

#### [3 线程间通信与同步](slides/instruction/principleWindows_3.pptx)

#### [4 文件系统管理](slides/instruction/principleWindows_4.pptx)

#### [5 WINDOWS 注册表](slides/instruction/principleWindows_5.pptx)

#### [6 动态链接库](slides/instruction/principleWindows_6.pptx)

#### [7 COM](slides/instruction/principleWindows_7.pptx)

#### [8 消息与事件](slides/instruction/principleWindows_8.pptx)


[返回目录](#index)


## 1 Visual Studio 2019 Community

### 1.1 Installation of VS 2019 Community

### [1.2 Choice of Front-end Frameworks](appendix/front-end.md)


[返回目录](#index)



## 2 git, github and gitee

本课程采用 git 作为项目管理工具并管理课程相关教学、训练及练习资源。
建议大家以 github 作为主要的远程仓库方便获取丰富的程序员社区资源，
而将 gitee 作为备份远程仓库来备份源码以备不时之需。尽量同时采用 github 
与 gitee 来保存个人的源码及编码资源。

[git 下载地址 https://git-scm.com/downloads](https://git-scm.com/downloads)

从上述官网下载 git 的最新版本进行缺省安装即可。

### 2.1 SSH Connection

使用 git 工具来管理项目, 通常会使用 SSH 来连接代码仓库。win10 下如何
安装 SSH client 参见:

[win10 安装SSH](git/ssh_client.md)


生成并使用 ssh-key:

[参见 ssh-key](git/ssh_gitee.md)


### 2.2 Push to Remote Repositories

同步本地仓库到 github 与 gitee 的方法参见：

[同步推送本地仓库到 gitee 与 github](git/gitee_n_github.md)

#### 2.2.1  github

github extension 的安装参见教学幻灯片。

#### 2.2.2  gitee

事实上 github extension 已经可以涵盖 gitee extension 的作用。
gitee 的 VS extension 下载地址:

https://marketplace.visualstudio.com/items?itemName=GiteeInc.GiteeExtension

### [2.3 frequently used git commands](git/frequentlyUsed.md)

### [2.4 New git preview features](git/preview_features.md)


[返回目录](#index)


## 3  WSL

[Installation of WSL](WSL/WSL.md)


[返回目录](#index)


## 4 Course Lab

[Goto details](labs/labs.md)

### 4.1 git

basic git command

pull request

### 4.2 tools

*  DUMPBIN \
https://docs.microsoft.com/en-us/cpp/build/reference/dumpbin-reference?view=vs-2019
\
https://www.cnblogs.com/zhaotianff/p/10637397.html

*  readelf \
https://www.cnblogs.com/gatsby123/p/9750187.html


[返回目录](#index)


## 5 refs

<https://github.com/microsoft>

[C++/winRT refs](appendix/cppWinRT.md)
[Rust/winRT refs](appendix/rustWinRT.md)


[返回目录](#index)


## 6 Academic Integrity

Grading in this course is intended to be fair and objectively measure your 
performance as much as possible. 
Wuhan University regards acts of academic dishonesty (e.g., plagiarism, 
cheating on examinations, obtaining unfair advantage, and falsification of 
laboratory notebook records) as serious offenses against the values of 
intellectual honesty. 

Penalty for Academic Dishonesty:
* grade penalty: final grade is of 0 grade-point


[返回目录](#index)


## 7 How to contribute

1.  Create a personal fork
2.  Clone the fork on your local machine
3.  Create a new feature branch Feat_xxx 
4.  Make a commit
4.  Create new Pull Request


[返回目录](#index)


## 8 Preprint of Text

**编写教材预印本**, **欢迎大家增加素材或贡献工作！**

[第1章 概述](preprint/chapter_1/ch_1.md)

[第2章 进程](preprint/chapter_2/ch_2.md)

[第3章 线程](preprint/chapter_3/ch_3.md)

[第4章 文件系统](preprint/chapter_4/ch_4.md)

[第5章 注册表](preprint/chapter_5/ch_5.md)

[第6章 动态链接库](preprint/chapter_6/ch_6.md)

[第7章 COM 原理](preprint/chapter_7/ch_7.md)

[第8章 窗体与消息](preprint/chapter_8/ch_8.md)


[返回目录](#index)



- [Registration-Free COM Interop](https://docs.microsoft.com/en-us/dotnet/framework/interop/registration-free-com-interop)
- [Enhancing Non-packaged Desktop Apps using Windows Runtime Components](https://blogs.windows.com/windowsdeveloper/2019/04/30/enhancing-non-packaged-desktop-apps-using-windows-runtime-components/)
- [RegistryHive Enum](https://docs.microsoft.com/en-us/dotnet/api/microsoft.win32.registryhive?view=net-6.0)
- [Windows Messages](https://flylib.com/books/en/4.460.1.19/1/)
- [A Thread s Message Queue](https://flylib.com/books/en/4.419.1.175/1/)
- 书籍素材 [Programming Applications for Microsoft Windows (Microsoft Programming Series)](https://flylib.com/books/en/4.419.1/)
