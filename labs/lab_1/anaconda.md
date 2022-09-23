# anaconda

*****************************

## Index

0. [Why anaconda?](#why-anaconda)
1. [Installation](#installation) 
2. [Environment management](#environment-management)
6. [msys2 and anaconda](#msys2-and-anaconda)


## 0 Why anaconda?

先来解决一个初学者都会问的问题：我已经安装了 Python，那么为什么还需要 Anaconda 呢？原因有以下几点：

1. Anaconda 附带了一大批常用数据科学包，它附带了 conda、Python 和 150 多个科学包及其依赖项。因此你可以用 
Anaconda 立即开始处理数据。

2. 管理包。\
Anaconda 是在 conda (一个包管理器和环境管理器)上发展出来的。在数据分析中，你会用到很多第三方的包，而 
conda(包管理器)可以很好的帮助你在计算机上安装和管理这些包，包括安装、卸载和更新包。

3. 管理环境。\
为什么需要管理环境呢？比如你在 A 项目中用到了 Python2，而新的项目要求使用 Python3，而同时安装两个 Python 
版本可能会造成许多混乱和错误。这时候 conda 就可以帮助你为不同的项目建立不同的运行环境。还有很多项目使用的包版本不同，
比如不同的 pandas 版本，不可能同时安装两个 pandas 版本。你要做的应该是在项目对应的环境中创建对应的 pandas 
版本。这时候 conda 就可以帮你做到。

[Back to index](#index)


## 2 Installation

到 https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/ 下载安装。

### 2.1 config environment variables

将以下路径添加到系统环境变量中:
- D:\ProgramData\Anaconda3;
- D:\ProgramData\Anaconda3\Scripts;
- D:\ProgramData\Anaconda3\Library\mingw-w64\bin;
- D:\ProgramData\Anaconda3\Library\usr\bin;
- D:\ProgramData\Anaconda3\Library\bin;

### 2.2 设置镜像站点

使用 conda install 包名 安装需要的 Python 非常方便，但是官方的服务器在国外，因此下载速度很慢。国内清华大学提供了 
Anaconda 的仓库镜像，我们只需要配置 Anaconda 的配置文件，添加清华的镜像源，然后将其设置为第一搜索渠道即可。cmd 
命令行下分别执行以下命令：
```batch
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
```

### 2.3 测试是否安装正确

在 cmd/powershell 命令下输入 conda info 可以查看是否已安装成功。
```batch
PS D:\> conda info

     active environment : None
       user config file : C:\Users\jiche\.condarc
 populated config files : C:\Users\jiche\.condarc
          conda version : 4.12.0
    conda-build version : 3.21.8
         python version : 3.9.12.final.0
       virtual packages : __cuda=11.6=0
                          __win=0=0
                          __archspec=1=x86_64
       base environment : d:\ProgramData\Anaconda3  (read only)
      conda av data dir : d:\ProgramData\Anaconda3\etc\conda
  conda av metadata url : None
           channel URLs : https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/win-64
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/noarch
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/win-64
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/noarch
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/win-64
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/noarch
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/win-64
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/noarch
                          https://repo.anaconda.com/pkgs/main/win-64
                          https://repo.anaconda.com/pkgs/main/noarch
                          https://repo.anaconda.com/pkgs/r/win-64
                          https://repo.anaconda.com/pkgs/r/noarch
                          https://repo.anaconda.com/pkgs/msys2/win-64
                          https://repo.anaconda.com/pkgs/msys2/noarch
          package cache : d:\ProgramData\Anaconda3\pkgs
                          C:\Users\jiche\.conda\pkgs
                          C:\Users\jiche\AppData\Local\conda\conda\pkgs
       envs directories : C:\Users\jiche\.conda\envs
                          d:\ProgramData\Anaconda3\envs
                          C:\Users\jiche\AppData\Local\conda\conda\envs
               platform : win-64
             user-agent : conda/4.12.0 requests/2.27.1 CPython/3.9.12 Windows/10 Windows/10.0.22000
          administrator : False
             netrc file : None
           offline mode : False

PS D:\>
```

[Back to index](#index)


## 2 Environment management

VS 有一个多环境管理工具的界面，配合命令行非常方便管理 python 运行所需要的多种环境，例如 pytorch 环境。

### 2.1 创建环境

```batch
# 创建 python3 版本的环境
conda create -n python3 python=3.9
```

### 2.2 激活环境
```batch
# 进入上面创建的 python3 环境
conda activate python3
```

### 2.3 拆除环境
```batch
# 拆除当前环境
deactivate
```

### 2.4 共享环境

共享环境非常有用，它能让其他人安装你代码中使用的所有包，并确保这些包的版本正确。比如你开发了一个系统，
你要提交给项目部署系统的人来部署你的项目，但是他们并不知道你当时开发时使用的是哪个 python 版本，
以及使用了哪些包和包的版本。这怎么办呢？你可以在你当前的环境的终端中使用:
```batch
# 将你当前的环境保存到文件中包保存为 YAML 文件
conda env export > environment.yaml
```
将你当前的环境保存到文件中包保存为 YAML 文件(包括 Pyhton 版本和所有包的名称)。命令的第一部分 conda env export 
用于输出环境中的所有包的名称(包括 Python 版本)。你在终端中上可以看到导出的环境文件路径。在 GitHub 
上共享代码时，最好同样创建环境文件并将其包括在代码库中。这能让其他人更轻松地安装你的代码的所有依赖项。

导出的环境文件，在其他电脑环境中如何使用呢？
首先在 conda 中进入你的环境，比如 conda activate python3。然后在使用以下命令更新你的环境：
```batch
# 其中 -f 表示你要导出文件在本地的路径，所以 /path/to/environment.yml 要换成你本地的实际路径
conda env update -f=/path/to/environment.yml
```

### 2.5 环境清单

有时候会忘记自己创建的环境名称，这时候用 conda env list 就可以列出你创建的所有环境。
```batch
(base) D:\>conda activate env_pytorch

(env_pytorch) D:\>conda env list
# conda environments:
#
env_pytorch           *  C:\Users\jiche\.conda\envs\env_pytorch
base                     d:\ProgramData\Anaconda3

(env_pytorch) D:\>
```

### 2.6 删除环境
```batch
# 删除指定的环境(在这里环境名为 python3)
conda env remove -n python3
```

[Back to index](#index)


## 6 msys2 and anaconda

参见 vsMem/tools/msys2.md#msys2-and-anaconda

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


