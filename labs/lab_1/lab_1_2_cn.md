# ʵ���: ���� windows Ӧ�ó���

go to [English Version](lab_1_2.md)

**�ο�:**
- <https://learn.microsoft.com/en-us/windows/apps/winui/winui3/create-your-first-winui3-app>
- <https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/simple-winui-example>
- <https://learn.microsoft.com/en-us/visualstudio/python/tutorial-working-with-python-in-visual-studio-step-00-installation>

***

�ڴ˴�ʵ���У����ǽ�ʹ�� Visual Studio 2022 ��64λ������������ Windows 11 
ƽ̨�¼��ֲ�ͬ���͵�����Ӧ�ó��򣬰�����
- C++ / WinUI 3 ����Ӧ�ó���
- C# / WinUI 3 ����Ӧ�ó���
- python Ӧ�ó���


## Ŀ¼ <span id="index"></span>

0. [ʵ��ǰ׼������](#prerequisites)
1. [���� C++/WinUI3 Ӧ�ó���](#create_cpp_winui3_app)
2. [���� C#/WinUI3 Ӧ�ó���](#create_cs_winui3_app)
3. [���� Python ������Ŀ](#create_python_proj)\
    [3.0 ��װ Python ����֧��](#3_0_install_python_support)\
    [3.1 �����µ� Python ������Ŀ](#3_1_create_new_python_project)\
    [3.2 ���벢����](#3_2_write_and_run_code)


## 0 ʵ��ǰ׼������ <span id="prerequisites"></span>

1. ��װ Visual Studio Community 2022, ѡ���������ΪӢ����� Tools > 
options > Environment > General > Color Theme ����Ϊ Dark

2. ����վ [Downloads for the Windows App SDK](https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads)
���ز��������°�� Windows App SDK **��װ����**��

3. ΪĿ���豸�������������ʵ��ļ��������װ [Microsoft Visual C++ Redistributable (VCRedist)](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist)��
> ���δ��Ŀ���豸��װ�� VCRedist �ַ������ᵼ��������ʵ���Ŀ�����ʱ�����޷����ӵ���̬���ӿ�
`c:\windows\system32\vcruntime140.dll` �Ĵ���

[�ص�Ŀ¼](#index)


## 1 ���� C++/WinUI3 Ӧ�ó��� <span id="create_cpp_winui3_app"></span>

1. �� Visual Studio 2022 Community (��� continue without codes)
(����ֱ�ӵ��Create a new project����������)

![open VS](pix/splashVS.PNG)

2. �� Visual Studio �в˵���ѡȡ File > New > Project��

![new project](pix/newProject.PNG)

3. �� Create a new project �Ի�������Ϸ�������ѡ��˵��зֱ�ѡ�� [c++], 
[Windows], [WinUI]

![create a new project](pix/createApp.PNG)

4. Ϊ����ʹ�� XAML �����Ҫ���� MSIX-packaged ������Ŀ���������޸ģ����������
�ڳ��ֵ���Ŀ������ѡ�� **Blank App, Packaged (WinUI 3 in Desktop)** 
������Ŀģ��, Ȼ���� `Next`��
\
�����Ӧ�ó������Ϳɸ�����Ҫѡ��������Ŀ���͡�

5. ��д�������Ĺ������ơ����λ�ü�����������ƺ��� Create ��ť

![Config the new project](pix/configProject.PNG)

6. Ȼ��ȴ�...

![Creating project](pix/creating.PNG)

7. ��������Ӧ�ó��򹤳�

![the generated project](pix/projectGenerated.PNG)

8. ѡ�� active solution platform Ϊ x64

![config active solution platform to be x64](pix/activeSolutionPlatform.PNG)

9. �� `Solution Explorer` ���Ҽ����������Ŀ���� `HelloWinUI_cpp` �����˵���ѡ��
`Unload Project`, �����ͻ�رյ�ǰ���б༭�ĵ��Ĵ��ڡ�

![the generated project](pix/unload_project.jpg)

���һ�������Ŀ���� `HelloWinUI_cpp` �����˵���ѡ�� `Edit Project File` ���ǾͿ����޸���Ŀ�Ĺ����ļ�

10. �������������Լӵ���չ��Ϊ HelloWinUI_cpp.vcxproj ����Ŀ�����ļ��С��������е� PropertyGroup 
Ԫ����:
```xml
<Project ...>
  ...
  <PropertyGroup Label="Globals">
    ...
    <WindowsPackageType>None</WindowsPackageType>
    <AppxPackage>false</AppxPackage>
    ...
  </PropertyGroup> 
  ...
</Project>
```
����ԭ����
```xml
    <AppxPackage>true</AppxPackage>
```
�е� `true` ��Ҫ���ĳ� `false`��

11. �Ҽ������Ŀ���ƺ��ڵ����Ĳ˵���ѡ�� build ��ʼ���ɸ���Ŀ��Ӧ��

![build the project](pix/buildProject.PNG)

12. ����ݼ� F5 �ɵ������иó���

![Press shortcut F5 to run](pix/runDebug.PNG)

��һ�����л�Ƚ����������ĵȴ���

> ����Ĳ��� 9 �벽�� 10 ���ֹ��޸ĵķ��������� VS �� App SDK ֧�ֵ����ƣ�δ���������᲻��Ҫ�ֹ����С�

[�ص�Ŀ¼](#index)


## 2 ���� C#/WinUI3 Ӧ�ó��� <span id="create_cs_winui3_app"></span>

1. �� Visual Studio �в˵���ѡȡ File > New > Project��

2. �ڳ��ֵ��½�������Ŀ�Ի�������������б����зֱ�ѡ�� C#, Windows, �� WinUI ѡ�

3. ��ǰһ�����ƵĲ��贴��������Ŀ `HelloWinUI_cs`, �����뵽ǰ�洴���� Solution `HelloWinUI` �С�

4. �������������Լӵ���չ��Ϊ .csproj �Ĺ�����Ŀ�ļ��С��������е� PropertyGroup 
Ԫ����:
```xml
<Project ...>
  ...
  <PropertyGroup>
    ...
    <WindowsPackageType>None</WindowsPackageType>
  </PropertyGroup> 
  ...
</Project>
```

5. ���������� debugging ��ʽ���� without debugging ��ʽ��������һ�� C# Ӧ�ó���Ҫ�����������˵���
ѡȡ unpackaged ���������ļ������ѡȡ Package �����ļ�������� Visual Studio �г��ֲ������
�����ͨ�������л��� Windows �ļ������������Ӧ�ó��� (.exe) ����һ������ʡ�ԡ�

![Select the package type](pix/package_type.png)

6. ������Ŀ�����С�

[�ص�Ŀ¼](#index)


## 3. ���� Python ������Ŀ <span id="create_python_proj"></span>


### 3.0 ��װ Python ����֧�� <span id="3_0_install_python_support"></span>

1. �� Visual Studio �ڲ˵���ѡȡ `Tools` > `Get Tools and Features` �����а�װ VS��

2. ѡ�� `Python ������������` ����� **��װ**

3. ���Ҫ���ٲ��� Python ֧��, ���� Visual Studio, ���� Alt+I �� Python 
��������, ���� `2+2` ��س�. ���û�м������Ϊ 4, ����Ҫ���¼�鰲װ�����Ƿ�������

[�ص�Ŀ¼](#index)


### 3.1 �����µ� Python ������Ŀ <span id="3_1_create_new_python_project"></span>

1. ���� Visual Studio, ѡ�� `File` > `New` > `Project` ���߰���ݼ� `Ctrl+Shift+N` 
���������¹�����Ŀ����Ļ��ʾ������������������ͬ��ģ�弰��ͬ�ı������ѡ��

2. ���½�������Ŀ�������˵�����ѡ���У�ѡ�� Python ���ԡ�
![new python project](pix/new_python_proj.png)

3. ѡ�� Python Ӧ�ã�Ȼ���� `Next`��

4. �� `Configure your new project` �����У��趨������Ŀ�����Ƽ��ļ�λ�ã�
����� **Create**��
\
����������������Ŀ HelloWorld_python ���� Visual Studio �д򿪡�
    - Visual Studio �ġ����������Դ�����������ڽ���ʾ��Ŀ�ṹ (1) ��
    - Ĭ�ϴ����ļ����ڱ༭���д� (2)��
    - �����ԡ����ڽ���ʾ�ڡ����������Դ����������ѡ������������Ϣ���������ڴ����ϵ�ȷ��λ�� (3) ��

![getting started python windows](pix/getting-started-python-windows.png)

[�ص�Ŀ¼](#index)


### 3.2 ���벢���� <span id="3_2_write_and_run_code"></span>

1. �����������Ŀ��ļ� `HelloWorld_python.py` ���Զ��� Visual Studio �༭���д򿪡�

2. �ڱ༭���У����� print("Hello, World!")

3. ��ݼ� `F5` �� `Ctrl+F5`��Ҳ����ѡ�� `Debug` > `Start Debugging` �� `Start without Debugging` �˵��
������������д�Ĵ��롣 ��������д��ڴ���Visual Studio �ᷢ�����档

4. ����̨���ڽ���ʾ���
```shell
Hello, World!
Press any key to continue . . .
```

[�ص�Ŀ¼](#index)








