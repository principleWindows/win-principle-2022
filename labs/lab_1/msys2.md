# msys2

- [�������MSYS2�Լ�δ����չ������Σ�](https://www.zhihu.com/question/37025275)
- [How To Set Up And Use MSys2](https://cadhut.com/2020/08/02/how-to-set-up-and-use-msys2/)
- [MSYS2](https://github.com/msys2)

*************************************

## Index

1. [What is msys2?](#what-is-msys2)
2. [Set up a ��Home��](#set-up-a-Home)
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

`msys2` ��һ���ŵ����������
`pacman` �����������û����ԱȽ����ɵ�ʹ�� `Linux` ���������ķ�ʽ����װһ���׿�����
`Windows` �����е� `Linux` ���ߡ����ֻ������ `Windows` �ϼ�����һЩ
`Linux` ������ô `msys2` ��һ���ܺõ�ѡ��

�� `/usr/bin` �ӽ��������� `path` �Ժ󣬿���ֱ���� `cmd` ��ʹ�� Linux ���
�൱�� Windows �����һ�� pacman ����������

MSys2 is a system that gives you 3 different shell environments:
- **MSYS2**: A system maintenance shell \
If you want to install packages or tools, you use this shell. 
You don��t use this shell to build software. \
���п���ʹ�ò��� linux ��ר�к��������� fork
- **MinGW32**: A 32-bit GCC build environment \
If you want to build software using 32-bit tools, you launch this shell. \
Note: *You can compile 64-bit binaries with 32-bit tools*
- **MinGW64**: A 64-bit GCC build environment \
If you want to build software using 64-bit tools, you launch this shell. \
Note: *You can build compile 32-bit binaries with 64-bit tools*

�� 2 �� windows ����������������ĳ���Ч�ʱȵ�һ�� msys2 �µ� gcc ��������ܸ��ߡ�
������Ϊʲôͨ���õ�һ��������ά�������ú������������ԭ��

������Ҫ���� windows �µ�ͼ�ι��ߣ��Ŷӻ����� VS �á����˿��� msys2 ������һ�档
����û�ҵ������ mingw �³���������� coredump �ļ��ķ�������� linux/windows 
���򶼿����Ļ���msys2 ��������� linux ϰ�ߵ������й��߻��ǱȽϺ��õģ����԰� msys2
��Ϊһ������ֿ�ʹ�ã������ minGW �汾�ģ�����ʹ�� minGW �汾�Ĺ��ߡ�
���ܼ������õ�:
- grep
- wget
- ftpgpg 
- curl ��ʱ��Щ�򵥵�http����
- ssh 
- sshpass ������sshʱ������
- git 
- dos2unix windows�µ��ļ�תlinux�����绻�з���֮ͬ���
- cmake Ҫװmingw�汾�ģ������޷�����vs�����ļ�
- ntldd �������ļ��������, -R�����ɵݹ�����������dll����Ҫʹ��ldd
- svn ż��Ҫ���ϲֿ���룬�õĲ��࣬��������װͼ�ν���
- ffmpeg ����ȥר������windows�汾��,ֱ��pacman -S�㶨
- md5sum ����md5��
- uuidgen ��������һ��uuid

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


## 2 Set up a ��Home��

This step is optional, but highly recommended. Many tools that have come from 
the Unix platform make use of an environment variable called ��HOME��. If you 
set one, then MSys2 will use that directory to store command-line history, 
your personal settings, etc.

The best place for a HOME directory is on a short directory path with no 
spaces. I generally put it in ��D:\Home��. If you don��t know how to do this, 
right click on ��My Computer��, choose ��Properties��, then follow the steps in 
the picture below.

![Setting-Environment-Variables.png](pix/Setting-Environment-Variables.png)

Note: The variable must be an upper-case ��HOME��, but the directory I use is ��Home��.\
**Advanced option**: I also put this Home directory under Git revision control, 
so I can track changes to my settings over time.

**ע�⣺**\
��װ�� MSYS2 ��/etc/pacman.d/ ����λ������ ��D:\Home��������λ�� MSYS2 �İ�װĿ¼ 
"file://D:/msys2_64/etc/pacman.d/"����Ӧ�ľ��������ļ�
"/etc/pacman.d/mirrorlist.msys" Ҳ��λ�����λ�á�

[Back to index](#index)


## 3 Installation

You can have as many copies of MSys2 on your PC as you like. If I��m trying 
something potentially risky that may mess up my configuration, I will either 
create a backup of my installation by making the ��.zip�� file of the whole 
thing, or I will make a new installation from scratch. I��ve started from 
scratch as I write this to make sure that I don��t miss any commands.

### 3.1 Download the installer

Go to the Tsinghua mirror site of MSys2 to download the latest installer:

https://mirrors.tuna.tsinghua.edu.cn/msys2/distrib/

�ҵ��ʺ��Լ�ϵͳ�ܹ��İ�װ��, ������ɺ�װ���ɡ�
Your installation should be on a short path which has no spaces in it 
(i.e. not in ��C:\Program Files��). I generally put it in ��D:\msys2_64��. Keep 
following the instructions to update the base system.
��һ�δ��Ժ�ῴ��һ���Ƚ�С�Ĵ��ڣ������޸�һ�����塢����ʲô�ġ�
�����װ����û�д�����ݷ�ʽ�Ļ��������ֶ�ȥ��װĿ¼����Ѱ�� `msys2.exe` �ļ���

### 3.2 Change the mirror site

`msys2` ����ʹ�� `pacman` ����װ����������Ե�һ��������Ȼ���޸ľ���Դ�ĵ�ַ�ˡ�
�༭����Դ�ļ��ķ����ܼ򵥣������� `msys2` �İ�װ·���� `D:\msys2_64`����������� 
`powershell` �ű����ɡ�����㰲װ·��������λ�ã��޸Ľű����ɡ�

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
**�� �����ű�������[mirror.ps1](mirror.ps1)�У���ȻҲ�����ֹ��޸���Ӧ�ľ��������ļ� ��**

Ȼ��Ϳ������ն������� `pacman -Syu` ����ϵͳ������ `archlinux` ������

`pacman.conf` sets `Architecture = auto` and it appears that `auto` uses 
`uname -m` which may result in `86_64`.
the msys mirror paths use `x86_64` not `86_64`
We can manually change pacman.conf to say `Architecture = x86_64`. 
This might be useful for some error mirror sites problems.

���Դ�޸ĺú󣬲�Ҫ�ż�������Ȳ���һ�����Դ�Ƿ���ã�
```batch
pacman -Sy
```

����������˼��ͬ������������ݿ⡣������������¼��䣬˵��û�����⣺
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

���������º��������:
```batch
pacman -Su
```
��������������ĸ��£�����ϵͳ���¡��м���Զ��˳���

��Ҫ�ż����´� MSys2������ MSys2 �İ�װĿ¼���ҵ� `autorebase.bat`��
˫�����С�Ȼ���ٴ� Msys2���鿴�����ļ������ݣ������ǽ��������뵽 PATH �С�

��һ������ǰ������**�������**��
```batch
pacman -Su
```

������ɺ�Ϳ��԰�װ git �ȹ�������ˣ�
```batch
pacman -S git
```
��װ Git ��˳�ְ� vim Ҳ��װ�ϡ�


[Back to index](#index)


## 4 How to use?

����ʹ�� `msys2` ģ�� `Linux` ����������һЩ `bash` �ű��Լ� `Linux` ����
�ܶೣ���ĳ��򶼿����� `msys2` ������ֿ����ҵ���`vim`��`nano`��`git` �ȳ��򶼿����������С�


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

�μ� [msys2 and anaconda](pyMem/anaconda.md#msys2-and-anaconda)

### 6.1 msys2
- **cygwin**: �������� windows ƽ̨�ϵ� POXIS ����ϵͳ�����ṩ Windows �µ��� Unix ϵͳ���ṩ window 
����ֲ Linux Ӧ�õĿ���������һ�����
- **MinGW**: �����ڽ��� windows Ӧ�ÿ����� GNU ������(��������)�����ı��������ԭ�� Windows Ӧ��
- **MSYS**: ���� MinGW ������������������� Windows �£����� cmd���Լ����׵������й��߲�����ȫ��Ҳ�����������ˣ�MinGW 
�����ߴ������ȽϾɵ� Cygwin ������һ����֧��Ҳ�����ṩ�� Unix ���������� Cygwin �Ĵ��ȫ��ͬ��MSYS 
�ǳ���С�������Ŀ��ȥ�ģ��������� MSYS �Լ� MinGW����Ҫ�Ի����� Linux ����Ϊ������С�� 200M ���ң�����û�ж�����չ������
- **msys2**: ���� MinGW ���겻���£�MSYS Ҳ�ǣ�Cygwin ������¹��ܲ���ͬ������������ Alex ���˽�������һ���� msys ��Ŀ ���� 
msys2, ʹ�ð������� pacman����Ȼ fork �� Cygwin (���°�)���л�Ծ�Ŀ����ߺ��û��顣�н϶�Ԥ������������

### 6.2 anaconda

�����ѧ����ʦ�Ǹ���������ڼ����ѧ�������the most popular Python data science platform. 
����˵ Anaconda �� Python ���ļ��ɻ���Ҳ���ǰ������������⻹�ǻ�����������

[Back to index](#index)

