# 3.1 创建非托管动态链接库

[English Version](lab_3_1.md)

这个实验改编自::
* [ref 1](https://learn.microsoft.com/en-us/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp)
* [ref 2](https://www.cnblogs.com/94cool/p/5772376.html)

***

## 第一部分:创建 c++ 非托管 DLL

在这部分的实验中，我们将为 c++ 非托管 DLL 创建一个项目并添加代码构建它。 首先，启动 Visual Studio 
2022 社区版并登录你在 whu 的学术账户，根据你正在使用的 Visual Studio 的版本，程序可能略有不同  


### 1.1 在 Visual Studio 2022 中创建一个 DLL 项目

1. 在菜单栏上，选择“文件>新建>项目”，打开“创建新项目”对话框。  

![create a new project](pix/new_project.png)

2. 在对话框的顶部，将语言设置为 c++，将平台设置为 Windows，  
并将项目类型设置为 Library.

3. 从筛选的项目类型列表中，选择动态链接库(DLL)，
然后选择 Next。

4. 在“Configure your new project”页面中，在项目名称”框中输入 “CreateDLL” 
为项目指定一个名称。选择默认位置并将解决方案名称设置为 
“dllTest”。如果已经勾选则取消勾选`Place solution and project in the same directory`。  

![config](pix/config.png)

5. 选择 `Create` 按钮来创建解决方案和项目。在创建解决方案时，您可以在
Visual Studio 中的“解决方案资源管理器”窗口查看。

![solution explorer](pix/solution_explorer.png)

目前，这个 DLL 并没有什么功能。接下来，将创建一个头文件来声明 DLL 
的导出函数，然后将函数定义添加到所创建的 DLL 中。

### 1.2 向 DLL 添加头文件

1. 创建函数的头文件：在菜单栏上，选择 `Project` > `Add New Item`。

2. 在 `Add New Item` 对话框的左侧选择 `Visual C++`。选择 `Header File (.h)`。指定 
`CreateDLL.h` 作为头文件的名称。

![add header file](pix/add_header.png)

3. 点击 `Add` 按钮生成一个空白头文件，该头文件将显示在新的编辑器窗口中。

![](pix/editor_window.png)

4. 用下面的代码替换头文件的内容:
```cpp
// CreateDLL.h - Contains declarations of unmanaged dll functions
#pragma once

#ifdef CREATEDLL_EXPORTS
#define CREATEDLL_API __declspec(dllexport)
#else
#define CREATEDLL_API __declspec(dllimport)
#endif

// 非托管动态链接库 DLL 的创建步骤:
// <1> 采用C++创建项目，项目类型为类库，名称为 CreateDLL

// <2> 在头文件中声明函数原型
extern "C" CREATEDLL_API int __stdcall testAdd (int a, int b);
extern "C" CREATEDLL_API int __stdcall testMulti (int a, int b);
```

注意文件顶部的预处理器语句的新项目模板，DLL 项目将 PROJECTNAME_EXPORTS 
添加到预定义的预处理器宏中。例如，当构建 “CreateDLL” DLL 项目时，Visual 
Studio 定义了 CREATEDLL_EXPORTS 的新项目模板。DLL 项目将 
PROJECTNAME_EXPORTS 添加到预定义的预处理器宏中。  

定义 CREATEDLL_EXPORTS 宏时，CREATEDLL_EXPORTS_API 宏设置函数声明中的 
`__declspec(dllexport)` 修饰符。 这个修饰符告诉编译器和链接器从 DLL 
中导出函数或变量以供其他人使用应用程序。 当 CREATEDLL_EXPORTS 
未定义时，例如，当头文件为由客户端应用程序包含，CREATEDLL_API 应用 
__declspec(dllimport) 修饰符到声明。 此修饰符优化函数或变量的导入应用。 

右键单击项目名称 `CreateDLL` 并选择 `Properties` 打开 `Property Pages`:

![](pix/preprocessor.png)

注意 CREATEDLL_EXPORTS 宏定义在 `Preprocessor Definitions`!


### 1.3 将实现添加到DLL中

1. 在解决方案资源管理器中，右键单击“源文件”节点并选择“添加”>“新项目”。创建一个名为 
`CreateDLL.cpp` 的新 .cpp 文件。其方式与你在上一步中添加新头文件的方式相同。

![add implementing file](pix/add_implementing.png)

2. 在编辑器窗口中，选择 CreateDLL.cpp 选项卡（如果它已经打开）。
如果没有，在解决方案资源管理器中双击，在 CreateDLL 项目的 `Source Files` 
文件夹中的 `CreateDLL.cpp` 并打开它。

3. 在编辑器中，用以下代码替换CreateDLL.cpp文件的内容:  

```cpp
// CreateDLL.cpp : Defines the exported functions for the DLL.

// 非托管动态链接库DLL的创建步骤:
// <3> 在cpp源代码文件中引用头文件，并实现函数

#include "pch.h"
#include "CreateDLL.h"

int __stdcall testAdd( int a, int b )
{
	return	a + b;
}

int __stdcall testMulti( int a, int b )
{
	return	a * b;
}
```

要验证到目前为止一切正常，需要编译动态链接库。编译：在菜单栏上选择 
`Build > Build Solution`。DLL 和相关编译器输出放在解决方案文件夹下面的一个名为 
`Debug` 的文件夹中。如果你创建一个发布版本时，输出放在名为 `Release` 
的文件夹中。输出应该如下所示：

```batch
Build started...
1>------ Build started: Project: CreateDLL, Configuration: Debug x64 ------
1>Environment at start of build:
1>ALLUSERSPROFILE                = C:\ProgramData
1>APPDATA                        = C:\Users\jiche\AppData\Roaming
1>ChocolateyInstall              = C:\ProgramData\chocolatey
1>VisualStudioEdition            = Microsoft Visual Studio Community 2022
1>VisualStudioVersion            = 17.0
1>VSAPPIDNAME                    = devenv.exe
1>VSSKUEDITION                   = Community
1>windir                         = C:\WINDOWS
1>pch.cpp
1>CreateDLL.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library F:\teaching\principleWindows\git\dllTest\x64\Debug\CreateDLL.lib and object F:\teaching\principleWindows\git\dllTest\x64\Debug\CreateDLL.exp
1>CreateDLL.vcxproj -> F:\teaching\principleWindows\git\dllTest\x64\Debug\CreateDLL.dll
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========

```

至此为止，你已经使用 `Visual Studio` 创建了一个 `DLL`! 
接下来，将创建一个来使用上述所创建的 `DLL` 的导出函数的客户端应用程序。


## 第二部分：创建使用 DLL 的 c# 客户端应用程序


### 2.1 在 `Visual Studio` 中创建一个客户端应用程序

1. 保持在第一部分中创建的解决方案处于打开状态。 在菜单栏上，选择 
`File > New > Project` 以打开 `Create a New Project` 对话框。

![create a new C# project](pix/new_project_cs.png)

2. 在对话框的顶部，设置语言为 `c#`，设置平台为 `Windows`，并将项目类型设置为 `Console`。

3. 从筛选的项目类型列表中，选择 `Console App(. NET Framework)`, 然后点击 `Next`。

4. 在 `Configure your new project` 页面中，在 `Project name` 
框中输入 `TestDLL` 为项目指定一个名称。选择默认位置并将解决方案设置为 
`Add to solution`。选择 `Framework` 为 `.NET Framework 4.8`。

![config](pix/config_cs.png)

5. 点击 `Create` 按钮来创建项目并将其添加到当前解决方案中。

在创建完成后，你可以在 `Visual Studio` 中的 `Solution Explorer` 查看该项目。

![solution explorer](pix/solution_explorer_all.png)

6. 右键单击项目的名称 `TestDLL`，并将其设置为 `Start up Project`。  


### 2.2 添加 c# 类来声明所导入 DLL 的函数 <span id="to-add-a-c-class-to-declare-functions-of-the-imported-dll"></span>

1. 右键单击Solution Explorer中的 `TestDLL`, 在菜单栏上选择 **add** > **Class...**，打开 
`Add New Item` 对话框。

![](pix/add_class_cs.png)

2. 选择 `Visual C# Items` ，选择 `Class`,输入编辑框的 `Name`：`DllTest.cs`。点击按钮 
`Add` 创建一个名为 `DllTest.cs` 的新的 `.cs` 文件并添加到项目中。

![](pix/add_class.png)

3. 在编辑器窗口中，选择 `DllTest.cs` 选修课(如果已经打开)。如果没有打开,在 `解决方案资源管理器` 
中，双击 `Source Files` 文件夹中的 `DllTest.cs` 来打开它。

4. 在编辑器中，用以下代码替换 `DllTest.cs` 的内容：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Runtime.InteropServices;
using System.Text;
using System.Threading.Tasks;

namespace TestDLL
{
    class DllTest
    {
        // 非托管动态链接库DLL的调用过程:
        // <1> 采用DllImport动态加载动态链接库文件中的函数
        // <2> 重新声明
        [DllImport(@"dll_cpp.dll", EntryPoint = "testAdd", SetLastError = true, CharSet = CharSet.Ansi, ExactSpelling = false, CallingConvention = CallingConvention.StdCall)]
        public static extern int testAdd(int a, int b);

        // 非托管动态链接库DLL的调用过程:
        // <1> 采用DllImport动态加载动态链接库文件中的函数
        // <2> 重新声明
        [DllImport(@"dll_cpp.dll", EntryPoint = "testMulti", SetLastError = true, CharSet = CharSet.Ansi, ExactSpelling = false, CallingConvention = CallingConvention.StdCall)]
        public static extern int testMulti(int a, int b);
    }
}
```

### 2.3 使用声明的函数

现在可以使用[上一步](#to-add-a-c-class-to-declare-functions-of-the-imported-dll)中所声明的函数。
用以下代码替换 `Program.cs` 中的内容:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace TestDLL
{
    class Program
    {
        static void Main(string[] args)
        {
            // 非托管动态链接库DLL的调用过程:
            // <3> 在程序中调用重新声明的函数
            int r1 = DllTest.testAdd(1, 2);

            int r2 = DllTest.testMulti(5, 2);

            Console.WriteLine("testAdd结果：" + r1.ToString());

            Console.WriteLine("testMulti结果：" + r2.ToString());

            Console.ReadKey();
        }
    }
}
```

这个客户端应用程序现在可以成功编译，但它仍然没有运行所需的一切。
当操作系统加载您的应用程序时，它会查找 `CreateDLL.dll`。
如果在某些系统目录、环境路径或本地应用程序目录中找不到该 DLL，则加载失败。 根据 
VS 的版本的不同，您将看到类似如下的错误消息：

![](pix/err_no_dll.png)

避免此问题的一种方法是将 `DLL` 复制到包含客户端可执行文件的目录中，作为构建过程的一部分。
你可以向项目添加一个 `Post-Build Event`，以添加一个将 DLL 复制到构建输出目录的命令。
这里指定的命令只在DLL缺失或已更改时复制它。它使用宏来复制，根据你的构建配置，进出调试或发布位置。

### 2.4 在 `Post-Build Event` 中复制 DLL

1. 右键单击“解决方案资源管理器”中的`TestDLL`节点，并选择 `Property`, 在编辑器窗口中打开。

2. 在左侧，选择 `Events > Post-Build Event`。

3. 在property中，单击`Edit Post-build...` 打开 `Post-Build Event` 命令行字段。输入下面命令:
```batch
xcopy /y /d "../../../x64\$(ConfigurationName)\CreateDLL.dll"
```
如果你的 DLL 和客户端项目在其他目录中，请将相对路径更改为匹配的 DLL。

4. 保存你对 `project properties` 的更改。

现在，你的客户端应用程序拥有构建运行所需的一切。通过在菜单栏上选择 `Build > Build Solution` 
来构建应用程序。 根据 `Visual Studio` 版本的差异，输出窗口中将出现类似以下的内容：

```batch
Build started...
1>------ Build started: Project: CreateDLL, Configuration: Debug x64 ------
2>------ Build started: Project: TestDLL, Configuration: Debug Any CPU ------
2>  TestDLL -> F:\teaching\principleWindows\git\dllTest\TestDLL\bin\Debug\TestDLL.exe
2>  找不到文件 - CreateDLL.dll
2>  复制了 0 个文件
1>pch.cpp
1>CreateDLL.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library F:\teaching\principleWindows\git\dllTest\x64\Debug\CreateDLL.lib and object F:\teaching\principleWindows\git\dllTest\x64\Debug\CreateDLL.exp
1>CreateDLL.vcxproj -> F:\teaching\principleWindows\git\dllTest\x64\Debug\CreateDLL.dll
========== Build: 1 succeeded, 1 failed, 0 up-to-date, 0 skipped ==========
```

有一个错误表明项目 `TestDLL` 无法找到项目 `CreateDLL` 生成的 dll 文件。
再次构建解决方案，错误就会消失，因为这次 `CreateDLL.dll` 已经在上次构建任务中构建了。

至此为止我们已经创建了一个调用 DLL 中函数的应用程序。现在运行你的应用程序以查看它的作用。
在菜单栏上，选择 `Debug > Start Without Debugging`。`Visual Studio` 打开一个命令窗口供程序运行。
最后一部分输出应如下所示：

![](pix/cmd.png)

按任意键关闭命令窗口。


## 2.5 调试 c# 项目中的非托管 c++ dll

现在你已经创建了一个 DLL 和一个客户端应用程序，你可以进行试验了。
尝试在客户端应用程序的代码中设置断点，并在调试器中运行该应用程序。看看当你进入库调用时会发生什么。
向库中添加其他函数，或编写另一个使用你的 DLL 的客户端应用程序。

但是此时如果在项目 `CreateDLL` 的代码中设置断点，则不会触发。要从 C# 
项目启用远程调试非托管 `C++ dll`，你可以通过勾选 `Enable native codes debugging` 
的选项来设置 `C#` 项目的属性，如下所示：

![](pix/enable_native_debugging.png)

保存此设置并再次运行 `Debugging`，在 `CreateDLL` 中设置的断点将会触发。
