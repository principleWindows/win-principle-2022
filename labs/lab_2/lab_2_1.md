# 实验1 进程及进程间通信

***

在此次实验中，我们将使用实验课框架代码 wpfTest 来观察 Windows 下的进程如何创建和调用子进程：
- 主进程创建子进程 ping 并同步调用之
- 主进程创建子进程 ping 并异步调用之
- 主进程创建子进程 getmac 并异步调用之


## 1 同步调用进程 ping

1. 在 wpfTest 的后台代码(code-behind) C2_SY1.xaml.cs 的第80行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至上一步所设置的断点处
3. 多次按快捷键 F10 逐行追踪代码的运行直到退出 `runCMD` 函数
4. 按快捷键 F5 直到返回界面

小结：重定向实现进程同步通信的步骤及过程。


## 2 异步调用进程 ping

1. 在 wpfTest 的后台代码(code-behind) C2_SY2.xaml.cs 的第172行 `clearComments();` 处按快捷键 F9 设置断点
2. 在 wpfTest 的后台代码(code-behind) C2_SY2.xaml.cs 的第217行 `cmdOutput.AppendLine(outLine.Data);` 处按快捷键 F9 设置断点
3. 运行 wpfTest 至第一步所设置的断点处
4. 按快捷键 F5 运行代码至第2步所设置的断点处
5. 多次按快捷键 F10 逐行追踪代码的运行直到退出 `strOutputHandler` 函数
6. 按快捷键 F5 直到返回界面

小结：重定向实现进程异步通信的步骤及过程。


## 3 异步调用进程 getmac

1. 在 wpfTest 的后台代码(code-behind) C2_SY3.xaml.cs 的第145行 `clearComments();` 处按快捷键 F9 设置断点
2. 在 wpfTest 的后台代码(code-behind) C2_SY3.xaml.cs 的第171行 `cmdOutput.AppendLine(outLine.Data);` 处按快捷键 F9 设置断点
3. 运行 wpfTest 至第一步所设置的断点处
4. 按快捷键 F5 运行代码至第2步所设置的断点处
5. 多次按快捷键 F10 逐行追踪代码的运行直到退出 `strOutputHandler` 函数
6. 按快捷键 F5 直到返回界面

对比：`2 异步调用进程 ping` 与 `3 异步调用进程 getmac` 有何异同？


