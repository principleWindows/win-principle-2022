# Create blank windows applications

- <https://learn.microsoft.com/en-us/windows/apps/winui/winui3/create-your-first-winui3-app>
- <https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/simple-winui-example>

***

In this experiment we are going to create several types of blank desktop applications on 
the Windows 11 platform:
- a blank C# / WinUI 3 desktop application
- a blank C++ / WinUI 3 desktop application
- a blank python application


## 0 Experiment requirements of software environment


## 1 Steps to create a C++/WinUI3 application

1. Download and run the latest *installer* for the Windows App SDK from [Downloads for the Windows 
App SDK](https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads).

2. Install the [Microsoft Visual C++ Redistributable (VCRedist)](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) 
appropriate for the architecture of the target device.
> If you don't have the VCRedist installed on the target device, then dynamic links to 
`c:\windows\system32\vcruntime140.dll` fail.

3. In Visual Studio, select File > New > Project.

4. In the New Project dialog's drop-down filters, select C++, Windows, and WinUI, respectively.

5. You need to start with an MSIX-packaged project in order to use XAML diagnostics. So select 
the **Blank App, Packaged (WinUI 3 in Desktop)** project template, and click Next.

6. Add the following two properties to your project file with extension .vcxproj. Put it inside the 
PropertyGroup element that's already there:
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

7. Build and run.
 


## 2 Steps to create a C#/WinUI3 application

Steps 1 through 3 are just the same as in the previous section. 

4. In the New Project dialog's drop-down filters, select C#, Windows, and WinUI, respectively.

Step 5 is the same as the one in the previous section

6. Add the following property to your project file with extension .csproj. Put it inside the 
PropertyGroup element that's already there:
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

7. To start a C# app from Visual Studio (either Debugging or Without Debugging), select the 
Unpackaged launch profile from the Start drop-down. If the Package profile is selected, then 
you'll see a deployment error in Visual Studio. This step isn't necessary if you start the 
application (.exe) from the command line or from Windows File Explorer.

![Select the package type](pix/package_type.PNG)

8. Build and run.


���Ľ�������� VS ������һ���յ�Ӧ�ó��������� Visual Studio 2019 Preview Community
Ϊ���ӽ�����������, VS 2017 �� VS 2019 �������汾�ɲο����С�

1. �� Visual Studio 2019 Community (��� continue without codes)(����ֱ�ӵ��Create a new project����������)

![open VS](pix/splashVS.PNG)

2. ��� File -> new -> Project

![new project](pix/newProject.PNG)

3. �� Create a new project �Ի������������ѡ��˵��ֱַ�ѡ�� [c++], 
[Windows], [WinUI], ���ڳ��ֵ���Ŀ������ѡ�� "App (WinUI 3 in Desktop)"
���� Next

![create a new project](pix/createApp.PNG)

�����Ӧ�ó������Ϳɸ�����Ҫѡ��������Ŀ���͡�

4. ��д�������Ĺ������ơ����λ�ü�����������ƺ��� Create ��ť

![Config the new project](pix/configProject.PNG)

5. ѡ��ȱʡ�Ĳ������� Create

![Select the target platform](pix/choosePlatform.PNG)

6. Ȼ��ȴ�...

![Creating project](pix/creating.PNG)

7. ��������Ӧ�ó��򹤳�

![the generated project](pix/projectGenerated.PNG)

8. ѡ�� active solution platform Ϊ x64

![config active solution platform to be x64](pix/activeSolutionPlatform.PNG)

9. �Ҽ������Ŀ���ƺ��ڵ����Ĳ˵���ѡ�� build ��ʼ���ɸ���Ŀ��Ӧ��

![build the project](pix/buildProject.PNG)

10. ����ݼ� F5 �ɵ������иó���

![Press shortcut F5 to run](pix/runDebug.PNG)

��һ�����л�Ƚ����������ĵȴ���

