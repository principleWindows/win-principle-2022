# pyTorch

- [GPU�汾PyTorch��ϸ��װ�̳�](https://blog.csdn.net/uuhhy/article/details/124638448)

*****************************

## Index

1. [�Կ�����](#video_card_setup)
   [1.1 �鿴�Կ��ͺ�)(#video_card_type) \
   [1.2 ���ذ�װ�Կ�����](#video_card_driver) \
   [1.3 �鿴GPU״̬](#video_card_status)
2. [CUDA](#cuda) \
   [2.1 Download CUDA](#download-cuda) \
   [2.2 Install CUDA](#install-cuda) \
   [2.3 Configure Env](#configure-env)
3. [cudnn](#cudnn)
4. [anaconda](#anaconda)
5. [PyTorch Installation](#pytorch-installation)

## 1 �Կ����� <span id="video_card_setup"></span>

### 1.1 �鿴�Կ��ͺ� <span id="video_card_type"></span>
1. �Ҽ������ʼͼ�꣬ѡȡ���豸��������
2. չ����ʾ�������鿴ϵͳ���Կ����ͺ�

![nvidia geforce rtx 3080](pix/rtx3080.png)

[Back to index](#index)


## 1.2 ���ذ�װ�Կ����� <span id="video_card_driver"></span>

���ص�����������Ϣ��

![driver](pix/gpu_driver_info.png)

������ɺ�����ʾ��װ���ɡ�

[Back to index](#index)


## 1.3 �鿴GPU״̬ <span id="video_card_status"></span>

�� cmd �ն����������� `nvidia-smi` �ɲ鿴 GPU ��״̬��

```shell
C:\Users\jiche>nvidia-smi
Thu Jun  9 12:04:55 2022
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 512.95       Driver Version: 512.95       CUDA Version: 11.6     |
|-------------------------------+----------------------+----------------------+
| GPU  Name            TCC/WDDM | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ... WDDM  | 00000000:02:00.0  On |                  N/A |
|  0%   48C    P8    17W / 370W |    447MiB / 10240MiB |      1%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|    0   N/A  N/A      4744    C+G   ...y\ShellExperienceHost.exe    N/A      |
|    0   N/A  N/A      7432    C+G   C:\Windows\explorer.exe         N/A      |
|    0   N/A  N/A      9128    C+G   ...ty\Common7\IDE\devenv.exe    N/A      |
|    0   N/A  N/A     12216    C+G   ...2txyewy\TextInputHost.exe    N/A      |
|    0   N/A  N/A     18120    C+G   ...ty\Common7\IDE\devenv.exe    N/A      |
|    0   N/A  N/A     19688    C+G   ...b3d8bbwe\ScreenSketch.exe    N/A      |
|    0   N/A  N/A     23460    C+G   ...bbwe\Microsoft.Photos.exe    N/A      |
+-----------------------------------------------------------------------------+
```

[Back to index](#index)


## 2 CUDA

### 2.1 Download CUDA

���ص�ַ���£� \
https://developer.nvidia.com/cuda-toolkit-archive

���������������µİ汾 11.7.0

[Back to index](#index)


### 2.2 Install CUDA

�Զ��尲װʱ�ǵ�ѡװ Visual Studio Integration.
�ҽ� CUDA ��װ���� D:/nvidia �ļ������ˡ�

[Back to index](#index)


### 2.3 Configure Env

1. �Ҽ������ʼͼ�꣬ѡȡ��ϵͳ�������ϵͳ��Ϣ�е�������Ӵ��ġ��߼�ϵͳ���á���
2. ��ϵͳ������������¼�������������\
   CUDA_LIB_PATH=%CUDA_PATH%\lib\x64 \
   CUDA_BIN_PATH=%CUDA_PATH%\bin

3. ��ϵͳ���� Path ��ĩβ��ӣ�\
    %CUDA_LIB_PATH%;%CUDA_BIN_PATH%;

[Back to index](#index)


## 3 cudnn

���ص�ַ���£� \
https://developer.nvidia.com/cudnn

���� cudnn ��ֱ�ӽ���⿪ѹ������Ȼ�󽫽�ѹ��� bin,include,lib �ļ��и���ճ����cuda
��װʱ��·���ļ����¡�

����cuda�Ƿ����óɹ���
```shell
C:\Users\root>nvcc -V
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2022 NVIDIA Corporation
Built on Tue_May__3_19:00:59_Pacific_Daylight_Time_2022
Cuda compilation tools, release 11.7, V11.7.64
Build cuda_11.7.r11.7/compiler.31294372_0
```

```shell
D:\nvidia\extras\demo_suite>deviceQuery.exe
deviceQuery.exe Starting...

 CUDA Device Query (Runtime API) version (CUDART static linking)

Detected 1 CUDA Capable device(s)

Device 0: "NVIDIA GeForce RTX 3080"
  CUDA Driver Version / Runtime Version          11.7 / 11.7
  CUDA Capability Major/Minor version number:    8.6
  Total amount of global memory:                 10240 MBytes (10736893952 bytes)
  (68) Multiprocessors, (128) CUDA Cores/MP:     8704 CUDA Cores
  GPU Max Clock rate:                            1800 MHz (1.80 GHz)
  Memory Clock rate:                             9501 Mhz
  Memory Bus Width:                              320-bit
  L2 Cache Size:                                 5242880 bytes
  Maximum Texture Dimension Size (x,y,z)         1D=(131072), 2D=(131072, 65536), 3D=(16384, 16384, 16384)
  Maximum Layered 1D Texture Size, (num) layers  1D=(32768), 2048 layers
  Maximum Layered 2D Texture Size, (num) layers  2D=(32768, 32768), 2048 layers
  Total amount of constant memory:               zu bytes
  Total amount of shared memory per block:       zu bytes
  Total number of registers available per block: 65536
  Warp size:                                     32
  Maximum number of threads per multiprocessor:  1536
  Maximum number of threads per block:           1024
  Max dimension size of a thread block (x,y,z): (1024, 1024, 64)
  Max dimension size of a grid size    (x,y,z): (2147483647, 65535, 65535)
  Maximum memory pitch:                          zu bytes
  Texture alignment:                             zu bytes
  Concurrent copy and kernel execution:          Yes with 1 copy engine(s)
  Run time limit on kernels:                     Yes
  Integrated GPU sharing Host Memory:            No
  Support host page-locked memory mapping:       Yes
  Alignment requirement for Surfaces:            Yes
  Device has ECC support:                        Disabled
  CUDA Device Driver Mode (TCC or WDDM):         WDDM (Windows Display Driver Model)
  Device supports Unified Addressing (UVA):      Yes
  Device supports Compute Preemption:            Yes
  Supports Cooperative Kernel Launch:            Yes
  Supports MultiDevice Co-op Kernel Launch:      No
  Device PCI Domain ID / Bus ID / location ID:   0 / 2 / 0
  Compute Mode:
     < Default (multiple host threads can use ::cudaSetDevice() with device simultaneously) >

deviceQuery, CUDA Driver = CUDART, CUDA Driver Version = 11.7, CUDA Runtime Version = 11.7, NumDevs = 1, Device0 = NVIDIA GeForce RTX 3080
Result = PASS
```

```shell
D:\nvidia\extras\demo_suite>bandwidthTest.exe
[CUDA Bandwidth Test] - Starting...
Running on...

 Device 0: NVIDIA GeForce RTX 3080
 Quick Mode

 Host to Device Bandwidth, 1 Device(s)
 PINNED Memory Transfers
   Transfer Size (Bytes)        Bandwidth(MB/s)
   33554432                     2989.5

 Device to Host Bandwidth, 1 Device(s)
 PINNED Memory Transfers
   Transfer Size (Bytes)        Bandwidth(MB/s)
   33554432                     3212.3

 Device to Device Bandwidth, 1 Device(s)
 PINNED Memory Transfers
   Transfer Size (Bytes)        Bandwidth(MB/s)
   33554432                     550389.7

Result = PASS

NOTE: The CUDA Samples are not meant for performance measurements. Results may vary when GPU Boost is enabled.
```


[Back to index](#index)


## 4. anaconda


https://blog.csdn.net/qq_45344586/article/details/124028689



[Back to index](#index)



## 5. PyTorch Installation

�� `Anaconda Prompt` ����Ӿ���Դ��
```shell
(base) C:\Users\root>conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
(base) C:\Users\root>conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
(base) C:\Users\root>conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
(base) C:\Users\root>conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
(base) C:\Users\root>conda config --set show_channel_urls yes
(base) C:\Users\root>
```

### 5.1 �������⻷����
```shell
(base) C:\Users\root>conda create -n env_pytorch python==3.9.7
(base) C:\Users\root>conda create -n your_env_name(���⻷������) python==xx(��Ҫ���������⻷����python�汾��)
```
���Ľ�����£�
```shell
done
#
# To activate this environment, use
#
#     $ conda activate env_pytorch
#
# To deactivate an active environment, use
#
#     $ conda deactivate
```


### 5.2 ��װPyTorch

�ȼ���������⻷��
```shell
(base) C:\Users\root>conda activate env_pytorch

(env_pytorch) C:\Users\root>
```
����������PyTorch������ѡ����ز�������ȡPyTorch��װָ�����anaconda prompt 
�ն���ִ�к�ɫ���е�ָ���ָ��Ϊ���°汾��PyTorch����

**ע�⣺��װ��ʱ��Ҫ��������-c pytorch���������ɾ�����ӹ���Դ�������أ��ٶȿ�һЩ��***


### 5.3 ��֤PyTorch�Ƿ�װ�ɹ�

��װ��ɺ󣬼�������anaconda prompt �ն���ִ������ָ���֤PyTorch�Ƿ�װ�ɹ���
```shell
python 
import torch 
torch.cuda.is_available() 
```
���ִ�н��Ϊtrue��˵����װ�ɹ���

��֤��ɺ�Ctrl+Z�ص������У�Ȼ��ִ��conda listָ��Ϳ��Կ��������⻷�����Ѿ���װ�õİ�

```shell
(env_pytorch) C:\Users\root>conda list
# packages in environment at C:\Users\jiche\.conda\envs\env_pytorch:
#
# Name                    Version                   Build  Channel
blas                      2.115                       mkl    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
blas-devel                3.9.0              15_win64_mkl    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
brotlipy                  0.7.0           py39hb82d6ee_1004    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
ca-certificates           2022.5.18.1          h5b45459_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
certifi                   2022.5.18.1      py39hcbf5309_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
cffi                      1.15.0           py39h0878f49_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
charset-normalizer        2.0.12             pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
cryptography              37.0.1           py39h21b164f_0    defaults
cudatoolkit               11.3.1               h59b6b97_2    defaults
freetype                  2.10.4               h546665d_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
idna                      3.3                pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
intel-openmp              2022.1.0          h57928b3_3787    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
jpeg                      9e                   h8ffe710_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
lcms2                     2.12                 h2a16943_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
lerc                      3.0                  h0e60522_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libblas                   3.9.0              15_win64_mkl    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libcblas                  3.9.0              15_win64_mkl    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libdeflate                1.10                 h8ffe710_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
liblapack                 3.9.0              15_win64_mkl    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
liblapacke                3.9.0              15_win64_mkl    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libpng                    1.6.37               h1d00b33_2    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libtiff                   4.3.0                hc4061b1_4    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libuv                     1.43.0               h8ffe710_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libwebp                   1.2.2                h57928b3_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libwebp-base              1.2.2                h8ffe710_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libxcb                    1.13              hcd874cb_1004    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
libzlib                   1.2.12               h8ffe710_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
lz4-c                     1.9.3                h8ffe710_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
m2w64-gcc-libgfortran     5.3.0                         6    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2
m2w64-gcc-libs            5.3.0                         7    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2
m2w64-gcc-libs-core       5.3.0                         7    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2
m2w64-gmp                 6.1.0                         2    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2
m2w64-libwinpthread-git   5.0.0.4634.697f757               2    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2
mkl                       2022.1.0           h6a75c08_874    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
mkl-devel                 2022.1.0           h57928b3_875    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
mkl-include               2022.1.0           h6a75c08_874    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
msys2-conda-epoch         20160418                      1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2
numpy                     1.22.4           py39h0948cea_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
openjpeg                  2.4.0                hb211442_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
openssl                   3.0.3                h8ffe710_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
pillow                    9.1.1            py39ha53f419_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
pip                       22.1.2             pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
pthread-stubs             0.4               hcd874cb_1001    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
pycparser                 2.21               pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
pyopenssl                 22.0.0             pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
pysocks                   1.7.1            py39hcbf5309_5    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
python                    3.9.7           h900ac77_3_cpython    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
python_abi                3.9                      2_cp39    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
pytorch                   1.11.0          py3.9_cuda11.3_cudnn8_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch
pytorch-mutex             1.0                        cuda    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch
requests                  2.27.1             pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
setuptools                62.3.3           py39hcbf5309_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
sqlite                    3.38.5               h8ffe710_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
tbb                       2021.5.0             h2d74725_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
tk                        8.6.12               h8ffe710_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
torchaudio                0.11.0               py39_cu113    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch
torchvision               0.12.0               py39_cu113    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch
typing_extensions         4.2.0              pyha770c72_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
tzdata                    2022a                h191b570_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
ucrt                      10.0.20348.0         h57928b3_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
urllib3                   1.26.9             pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
vc                        14.2                 hb210afc_6    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
vs2015_runtime            14.29.30037          h902a5da_6    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
wheel                     0.37.1             pyhd8ed1ab_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
win_inet_pton             1.1.0            py39hcbf5309_4    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
xorg-libxau               1.0.9                hcd874cb_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
xorg-libxdmcp             1.1.3                hcd874cb_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
xz                        5.2.5                h62dcd97_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
zlib                      1.2.12               h8ffe710_0    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
zstd                      1.5.2                h6255e5f_1    https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge

(env_pytorch) C:\Users\root>
```

[Back to index](#index)


