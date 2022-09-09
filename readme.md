# Windows Principles and Its Applications

[中文版](readme_cn.md)

[The Most Important New Features in Windows 11](https://www.msn.com/en-us/news/technology/the-most-important-new-features-in-windows-11/ar-AALpuhh)

**********************************

**Please leve your comment, suggestion, question in the comment feedback or send me emails!**

This is the teaching resource repository for the courses of CS, Wuhan University:
* Course No.(2022-2023-1)-3350520011035-SE "Windows principle and its applications"

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

Instructor: Professor Jicheng Hu


## Index

0. [Introduction](#introduction)
1. [Visual Studio 2022 Community](#visual-studio-2022-community)
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

#### [1 Introduction to Windows OS](slides/coursePPT/01Introduction2WindowsOS.pptx)

#### [2 Program and Process](slides/coursePPT/02process.pptx)

#### [3 Threads and Synchronization](slides/coursePPT/03thread.pptx)

#### [4 Management of File System](slides/coursePPT/04fs.pptx)

#### [5 WINDOWS Registry](slides/coursePPT/05registry.pptx)

#### [6 Dynamic Link Library](slides/coursePPT/06dll.pptx)

#### [7 COM](slides/coursePPT/07COM.pptx)

#### [8 Message and Event](slides/coursePPT/08msg_n_events.pptx)

### 0.2 instructional slides:

#### [0 Course Introduction](slides/instruction/introduction.pptx)

#### [1 Introduction to Windows Dev](slides/instruction/principleWindows_1.pptx)

#### [2 Program and Process](slides/instruction/principleWindows_2.pptx)

#### [3 Threads and Synchronization](slides/instruction/principleWindows_3.pptx)

#### [4 Windows File System](slides/instruction/principleWindows_4.pptx)

#### [5 WINDOWS Registry](slides/instruction/principleWindows_5.pptx)

#### [6 Dynamic Link Library](slides/instruction/principleWindows_6.pptx)

#### [7 COM](slides/instruction/principleWindows_7.pptx)

#### [8 Message and Event](slides/instruction/principleWindows_8.pptx)


[Back to index](#index)


## 1 Visual Studio 2022 Community

### 1.1 Installation of VS 2022 Community

### [1.2 Choice of Front-end Frameworks](appendix/front-end.md)


[Back to index](#index)


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


[Back to index](#index)


## 3  WSL

[Installation of WSL](WSL/WSL.md)


[Back to index](#index)


## 4 Course Lab

[Goto details](labs/labs.md)

### 4.1 git

basic git command

pull request

### 4.2 tools

*  DUMPBIN \
https://docs.microsoft.com/en-us/cpp/build/reference/dumpbin-reference?view=vs-2022
\
https://www.cnblogs.com/zhaotianff/p/10637397.html

*  readelf \
https://www.cnblogs.com/gatsby123/p/9750187.html


[Back to index](#index)


## 5 refs

<https://github.com/microsoft>

[C++/winRT refs](appendix/cppWinRT.md)
[Rust/winRT refs](appendix/rustWinRT.md)


[Back to index](#index)


## 6 Academic Integrity

Grading in this course is intended to be fair and objectively measure your 
performance as much as possible. 
Wuhan University regards acts of academic dishonesty (e.g., plagiarism, 
cheating on examinations, obtaining unfair advantage, and falsification of 
laboratory notebook records) as serious offenses against the values of 
intellectual honesty. 

Penalty for Academic Dishonesty:
* grade penalty: final grade is of 0 grade-point


[Back to index](#index)


## 7 How to contribute

1.  Create a personal fork
2.  Clone the fork on your local machine
3.  Create a new feature branch Feat_xxx 
4.  Make a commit
4.  Create new Pull Request


[Back to index](#index)


## 8 Preprint of Text

**Make contribution to our text preprint**, 
**add resources or sections to the following topics:**

[Chapter 1 Introduction](preprint/chapter_1/ch_1.md)

[Chapter 2 Process](preprint/chapter_2/ch_2.md)

[Chapter 3 Threads](preprint/chapter_3/ch_3.md)

[Chapter 4 File System](preprint/chapter_4/ch_4.md)

[Chapter 5 Registry](preprint/chapter_5/ch_5.md)

[Chapter 6 Dynamic Link Library](preprint/chapter_6/ch_6.md)

[Chapter 7 Windows COM](preprint/chapter_7/ch_7.md)

[Chapter 8 Windows and Messages](preprint/chapter_8/ch_8.md)


[Back to index](#index)



