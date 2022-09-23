# anaconda

*****************************

## Index

0. [Why anaconda?](#why-anaconda)
1. [Installation](#installation) 
2. [Environment management](#environment-management)
6. [msys2 and anaconda](#msys2-and-anaconda)


## 0 Why anaconda?

�������һ����ѧ�߶����ʵ����⣺���Ѿ���װ�� Python����ôΪʲô����Ҫ Anaconda �أ�ԭ�������¼��㣺

1. Anaconda ������һ�����������ݿ�ѧ������������ conda��Python �� 150 �����ѧ��������������������� 
Anaconda ������ʼ�������ݡ�

2. �������\
Anaconda ���� conda (һ�����������ͻ���������)�Ϸ�չ�����ġ������ݷ����У�����õ��ܶ�������İ����� 
conda(��������)���Ժܺõİ������ڼ�����ϰ�װ�͹�����Щ����������װ��ж�غ͸��°���

3. ��������\
Ϊʲô��Ҫ�������أ��������� A ��Ŀ���õ��� Python2�����µ���ĿҪ��ʹ�� Python3����ͬʱ��װ���� Python 
�汾���ܻ���������Һʹ�����ʱ�� conda �Ϳ��԰�����Ϊ��ͬ����Ŀ������ͬ�����л��������кܶ���Ŀʹ�õİ��汾��ͬ��
���粻ͬ�� pandas �汾��������ͬʱ��װ���� pandas �汾����Ҫ����Ӧ��������Ŀ��Ӧ�Ļ����д�����Ӧ�� pandas 
�汾����ʱ�� conda �Ϳ��԰���������

[Back to index](#index)


## 2 Installation

�� https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/ ���ذ�װ��

### 2.1 config environment variables

������·����ӵ�ϵͳ����������:
- D:\ProgramData\Anaconda3;
- D:\ProgramData\Anaconda3\Scripts;
- D:\ProgramData\Anaconda3\Library\mingw-w64\bin;
- D:\ProgramData\Anaconda3\Library\usr\bin;
- D:\ProgramData\Anaconda3\Library\bin;

### 2.2 ���þ���վ��

ʹ�� conda install ���� ��װ��Ҫ�� Python �ǳ����㣬���ǹٷ��ķ������ڹ��⣬��������ٶȺ����������廪��ѧ�ṩ�� 
Anaconda �Ĳֿ⾵������ֻ��Ҫ���� Anaconda �������ļ�������廪�ľ���Դ��Ȼ��������Ϊ��һ�����������ɡ�cmd 
�������·ֱ�ִ���������
```batch
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
```

### 2.3 �����Ƿ�װ��ȷ

�� cmd/powershell ���������� conda info ���Բ鿴�Ƿ��Ѱ�װ�ɹ���
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

VS ��һ���໷�������ߵĽ��棬��������зǳ�������� python ��������Ҫ�Ķ��ֻ��������� pytorch ������

### 2.1 ��������

```batch
# ���� python3 �汾�Ļ���
conda create -n python3 python=3.9
```

### 2.2 �����
```batch
# �������洴���� python3 ����
conda activate python3
```

### 2.3 �������
```batch
# �����ǰ����
deactivate
```

### 2.4 ������

�������ǳ����ã������������˰�װ�������ʹ�õ����а�����ȷ����Щ���İ汾��ȷ�������㿪����һ��ϵͳ��
��Ҫ�ύ����Ŀ����ϵͳ���������������Ŀ���������ǲ���֪���㵱ʱ����ʱʹ�õ����ĸ� python �汾��
�Լ�ʹ������Щ���Ͱ��İ汾������ô���أ���������㵱ǰ�Ļ������ն���ʹ��:
```batch
# ���㵱ǰ�Ļ������浽�ļ��а�����Ϊ YAML �ļ�
conda env export > environment.yaml
```
���㵱ǰ�Ļ������浽�ļ��а�����Ϊ YAML �ļ�(���� Pyhton �汾�����а�������)������ĵ�һ���� conda env export 
������������е����а�������(���� Python �汾)�������ն����Ͽ��Կ��������Ļ����ļ�·������ GitHub 
�Ϲ������ʱ�����ͬ�����������ļ�����������ڴ�����С������������˸����ɵذ�װ��Ĵ�������������

�����Ļ����ļ������������Ի��������ʹ���أ�
������ conda �н�����Ļ��������� conda activate python3��Ȼ����ʹ���������������Ļ�����
```batch
# ���� -f ��ʾ��Ҫ�����ļ��ڱ��ص�·�������� /path/to/environment.yml Ҫ�����㱾�ص�ʵ��·��
conda env update -f=/path/to/environment.yml
```

### 2.5 �����嵥

��ʱ��������Լ������Ļ������ƣ���ʱ���� conda env list �Ϳ����г��㴴�������л�����
```batch
(base) D:\>conda activate env_pytorch

(env_pytorch) D:\>conda env list
# conda environments:
#
env_pytorch           *  C:\Users\jiche\.conda\envs\env_pytorch
base                     d:\ProgramData\Anaconda3

(env_pytorch) D:\>
```

### 2.6 ɾ������
```batch
# ɾ��ָ���Ļ���(�����ﻷ����Ϊ python3)
conda env remove -n python3
```

[Back to index](#index)


## 6 msys2 and anaconda

�μ� vsMem/tools/msys2.md#msys2-and-anaconda

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


