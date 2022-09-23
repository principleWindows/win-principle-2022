# msys2

- [如何评价MSYS2以及未来发展方向如何？](https://www.zhihu.com/question/37025275)
- [How To Set Up And Use MSys2](https://cadhut.com/2020/08/02/how-to-set-up-and-use-msys2/)
- [MSYS2](https://github.com/msys2)

*************************************

## Index

1. [What is msys2?](#what-is-msys2)
2. [Set up a “Home”](#set-up-a-Home)
3. [Installation](#installation)
4. [How to use?](#how-to-use)
5. [How to find mingw64 redistributable dlls?](#how-to-find-mingw64-redistributable-dlls)
6. [msys2 and anaconda](#msys2-and-anaconda)

![](pix/MSYS2-Icon.png)


## 1 What is msys2?

Windows developers often need to use Unix-style commands and build 
software binary executables from source code. There are 3 main tools 
that let you do this:
- Cygwin
- MSys2
- Windows Subsystems for Linux (WSL)

MSYS2 is a collection of tools and libraries providing you with an 
easy-to-use environment for building, installing and running native 
Windows software. It consists of a command line terminal called mintty, 
bash, version control systems like git and subversion, tools like tar 
and awk and even build systems like autotools, all based on a modified 
version of Cygwin.

`msys2` 的一个优点就在于利用
`pacman` 包管理器，用户可以比较轻松的使用 `Linux` 包管理器的方式来安装一整套可以在
`Windows` 上运行的 `Linux` 工具。如果只是想在 `Windows` 上简单运行一些
`Linux` 程序，那么 `msys2` 是一个很好的选择。

把 `/usr/bin` 加进环境变量 `path` 以后，可以直接在 `cmd` 中使用 Linux 命令，
相当于 Windows 外挂了一个 pacman 包管理器。

MSys2 is a system that gives you 3 different shell environments:
- **MSYS2**: A system maintenance shell \
If you want to install packages or tools, you use this shell. 
You don’t use this shell to build software. \
其中可以使用部分 linux 下专有函数，比如 fork
- **MinGW32**: A 32-bit GCC build environment \
If you want to build software using 32-bit tools, you launch this shell. \
Note: *You can compile 64-bit binaries with 32-bit tools*
- **MinGW64**: A 64-bit GCC build environment \
If you want to build software using 64-bit tools, you launch this shell. \
Note: *You can build compile 32-bit binaries with 64-bit tools*

后 2 个 windows 开发环境编译出来的程序效率比第一个 msys2 下的 gcc 编译的性能更高。
这正是为什么通常用第一个环境做维护，而用后两个做编译的原因。

不过真要开发 windows 下的图形工具，团队还是用 VS 好。个人可以 msys2 环境玩一玩。
至今都没找到如何在 mingw 下程序崩溃生成 coredump 文件的方法。如果 linux/windows 
程序都开发的话，msys2 环境下许多 linux 习惯的命令行工具还是比较好用的，可以把 msys2
作为一个软件仓库使用，如果有 minGW 版本的，尽量使用 minGW 版本的工具。
介绍几个常用的:
- grep
- wget
- ftpgpg 
- curl 有时作些简单的http测试
- ssh 
- sshpass 可以在ssh时传密码
- git 
- dos2unix windows下的文件转linux，比如换行符不同之类的
- cmake 要装mingw版本的，否则无法生成vs工程文件
- ntldd 二进制文件依赖检测, -R参数可递归检测所有依赖dll，不要使用ldd
- svn 偶尔要看老仓库代码，用的不多，所以懒的装图形界面
- ffmpeg 不用去专门下载windows版本了,直接pacman -S搞定
- md5sum 生成md5的
- uuidgen 方便生成一个uuid

MSYS2 (Minimal SYStem 2) is an independent rewrite of MSYS, a (command-line) 
shell for development usage, and based on modern Cygwin (POSIX compatibility 
layer) and MinGW-w64 (from "MinGW-builds"), with the aim of better 
interoperability with native Windows software.

MSYS2 is a collection of tools and libraries providing you with an easy-to-use 
environment for building, installing and running native Windows software. It 
consists of a command line terminal called mintty, bash, version control systems 
like git and subversion, tools like tar and awk and even build systems like 
autotools, all based on a modified version of Cygwin. Despite some of these 
central parts being based on Cygwin, the main focus of MSYS2 is to provide a 
build environment for native Windows software and the Cygwin-using parts are 
kept at a minimum. MSYS2 provides up-to-date native builds for GCC, mingw-w64, 
CPython, CMake, Meson, OpenSSL, FFmpeg, Rust, Ruby, just to name a few. To 
provide easy installation of packages and a way to keep them updated it features 
a package management system called Pacman, which should be familiar to Arch 
Linux users. It brings many powerful features such as dependency resolution 
and simple complete system upgrades, as well as straight-forward and 
reproducible package building. The package repository contains more than 1800 
pre-built packages ready to install.

[Back to index](#index)


## 2 Set up a “Home”

This step is optional, but highly recommended. Many tools that have come from 
the Unix platform make use of an environment variable called “HOME“. If you 
set one, then MSys2 will use that directory to store command-line history, 
your personal settings, etc.

The best place for a HOME directory is on a short directory path with no 
spaces. I generally put it in “D:\Home“. If you don’t know how to do this, 
right click on “My Computer”, choose “Properties”, then follow the steps in 
the picture below.

![Setting-Environment-Variables.png](pix/Setting-Environment-Variables.png)

Note: The variable must be an upper-case “HOME”, but the directory I use is “Home”.\
**Advanced option**: I also put this Home directory under Git revision control, 
so I can track changes to my settings over time.

**注意：**\
安装完 MSYS2 后，/etc/pacman.d/ 不是位于上述 “D:\Home“，而是位于 MSYS2 的安装目录 
"file://D:/msys2_64/etc/pacman.d/"，相应的镜像配置文件
"/etc/pacman.d/mirrorlist.msys" 也就位于这个位置。

[Back to index](#index)


## 3 Installation

You can have as many copies of MSys2 on your PC as you like. If I’m trying 
something potentially risky that may mess up my configuration, I will either 
create a backup of my installation by making the ‘.zip’ file of the whole 
thing, or I will make a new installation from scratch. I’ve started from 
scratch as I write this to make sure that I don’t miss any commands.

### 3.1 Download the installer

Go to the Tsinghua mirror site of MSys2 to download the latest installer:

https://mirrors.tuna.tsinghua.edu.cn/msys2/distrib/

找到适合自己系统架构的安装包, 下载完成后安装即可。
Your installation should be on a short path which has no spaces in it 
(i.e. not in “C:\Program Files“). I generally put it in “D:\msys2_64“. Keep 
following the instructions to update the base system.
第一次打开以后会看到一个比较小的窗口，可以修改一下字体、语言什么的。
如果安装程序没有创建快捷方式的话，可以手动去安装目录里面寻找 `msys2.exe` 文件。

### 3.2 Change the mirror site

`msys2` 可以使用 `pacman` 来安装软件包，所以第一件事情自然是修改镜像源的地址了。
编辑镜像源文件的方法很简单，假设你 `msys2` 的安装路径是 `D:\msys2_64`，运行下面的 
`powershell` 脚本即可。如果你安装路径在其他位置，修改脚本即可。

```powershell
function InsertConentToFileTop {
    param(
        [String]$filename,
        [String]$content
    )
    $filecontent = Get-Content $filename
    $s = @()
    $s += $content
    $s += $filecontent
    $s | Out-File $filename
}

$msys2_install_dir = 'D:\msys2_64'
InsertConentToFileTop $msys2_install_dir\etc\pacman.d\mirrorlist.mingw32 'Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/i686'
InsertConentToFileTop $msys2_install_dir\etc\pacman.d\mirrorlist.mingw64 'Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/x86_64/'
InsertConentToFileTop $msys2_install_dir\etc\pacman.d\mirrorlist.msys 'Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/msys/x86_64/'
InsertConentToFileTop $msys2_install_dir\etc\pacman.d\mirrorlist.ucrt64 'Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/ucrt64/'
InsertConentToFileTop $msys2_install_dir\etc\pacman.d\mirrorlist.clang64 'Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/clang64/'
```
**（ 上述脚本保存在[mirror.ps1](mirror.ps1)中，当然也可以手工修改相应的镜像配置文件 ）**

然后就可以在终端中运行 `pacman -Syu` 更新系统，就像 `archlinux` 那样。

`pacman.conf` sets `Architecture = auto` and it appears that `auto` uses 
`uname -m` which may result in `86_64`.
the msys mirror paths use `x86_64` not `86_64`
We can manually change pacman.conf to say `Architecture = x86_64`. 
This might be useful for some error mirror sites problems.

软件源修改好后，不要着急打命令，先测试一下软件源是否可用：
```batch
pacman -Sy
```

这句命令的意思是同步本地软件数据库。如果看到了以下几句，说明没有问题：
```batch
jiche@gpuPower MSYS ~
$ pacman -Sy
:: Synchronizing package databases...
 mingw32 is up to date
 mingw64 is up to date
 ucrt64 is up to date
 clang64 is up to date
 msys is up to date
```


[Back to index](#index)


### 3.3 Update MSys2

接下来更新核心软件包:
```batch
pacman -Su
```
这句命令先做核心更新，再做系统更新。中间会自动退出。

不要着急重新打开 MSys2，先在 MSys2 的安装目录下找到 `autorebase.bat`，
双击运行。然后再打开 Msys2。查看该批文件的内容，发现是将环境加入到 PATH 中。

下一步继续前述步骤**更新软件**。
```batch
pacman -Su
```

更新完成后就可以安装 git 等工具软件了：
```batch
pacman -S git
```
安装 Git 会顺手把 vim 也安装上。


[Back to index](#index)


## 4 How to use?

可以使用 `msys2` 模拟 `Linux` 环境来运行一些 `bash` 脚本以及 `Linux` 程序。
很多常见的程序都可以在 `msys2` 的软件仓库中找到，`vim`、`nano`、`git` 等程序都可以正常运行。


[Back to index](#index)


## 5 How to find mingw64 redistributable dlls?

<https://github.com/msys2/setup-msys2/issues/150>

@WIN_DLL_PATH@/

If you are using mingw64 environment those are in `/mingw64/bin` folder. 
i.e. `${MINGW_PREFIX}/bin`

The `${MINGW_PREFIX}` variable is valid inside a running msys2/mingw64 
environment. So, you have to run that copy command in a shell script 
running in mingw64. I think you are using CI looking at the output. There 
may be other clever way to copy files. Wait for the experts

On powershell, you can use (& msys2 -c 'cygpath -w /') for getting the 
absolute path of the MSYS2 installation. See, for instance, 
https://github.com/umarcor/ghdl/blob/7743675de2bbb6e5fbe2d67cd0128ab1057f142e/.github/workflows/Test.yml#L493. 
That tests packages installed on MSYS2 from poweshell, using CPython.

[Back to index](#index)


## 6 msys2 and anaconda

参见 [msys2 and anaconda](pyMem/anaconda.md#msys2-and-anaconda)

### 6.1 msys2
- **cygwin**: 是运行在 windows 平台上的 POXIS “子系统”，提供 Windows 下的类 Unix 系统，提供 window 
上移植 Linux 应用的开发环境的一套软件
- **MinGW**: 是用于进行 windows 应用开发的 GNU 工具链(开发环境)，它的编译产物是原生 Windows 应用
- **MSYS**: 由于 MinGW 本身仅代表工具链，而在 Windows 下，由于 cmd，以及配套的命令行工具不够齐全（也不舒服），因此，MinGW 
开发者从曾经比较旧的 Cygwin 创建了一个分支，也用于提供类 Unix 环境。但与 Cygwin 的大而全不同，MSYS 
是冲着小巧玲珑的目标去的，所以整套 MSYS 以及 MinGW，主要以基本的 Linux 工具为主，大小在 200M 左右，并且没有多少扩展能力。
- **msys2**: 由于 MinGW 万年不更新，MSYS 也是，Cygwin 的许多新功能不能同步过来，于是 Alex 等人建立了新一代的 msys 项目 —— 
msys2, 使用包管理工具 pacman。仍然 fork 了 Cygwin (较新版)，有活跃的开发者和用户组。有较多预编译的软件包。

### 6.2 anaconda

计算科学工程师们搞出来的用于计算科学的软件，the most popular Python data science platform. 
简单来说 Anaconda 是 Python 包的集成环境也就是包管理器，另外还是环境管理器。

[Back to index](#index)

