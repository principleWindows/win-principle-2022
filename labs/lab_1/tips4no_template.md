
首先确保要将Win10和Visual Studio更新到最新版本（我电脑上VS是professional版本，以下方法是可行的，但是别的版本就不确定了）。接着有两种方法

1. 到[Project Reunion - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ProjectReunion.MicrosoftProjectReunion)下载安装

2. 通过Visual Studio的Manage Extension安装。

   ![image1](image/image1.png)

   这可能需要一段时间，安装完成后重启Visual Studio

3. 然后在项目模板中就可以找到Blank App, Package(WinUI in Desktop)，是符合实验要求的。

   ![image2](image/image2.png)

4. 接着创建项目，创建完成后系统会弹出设置页面，要求打开开发人员模式，打开。

   ![image3](image/image3.png)

5. 接着编译运行即可。

   ![image4](image/image4.png)



注意：项目路径中不能出现中文，否则编译会报错！