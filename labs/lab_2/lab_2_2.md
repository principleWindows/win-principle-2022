# 线程与线程间通信

在此次实验中，我们将使用实验课框架代码 wpfTest 来观察 Windows 
下线程的属性、如何创建线程及在线程间进行同步通信：
- 创建线程
- 获取当前线程的状态
- 线程间同步通信
- 线程间异步通信


## 1 线程


### 1.1 线程属性

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第92行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 多次按快捷键 F10 逐行追踪代码的运行直到退出 `btn1_Click` 函数
4. 按快捷键 F5 直到返回界面


### 1.2 创建线程

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第156行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 多次按快捷键 F10 逐行追踪代码的运行直到退出 `btn2_Click` 函数
4. 按快捷键 F5 直到返回界面

小结：创建线程的步骤。


### 1.3 前台线程先结束

本实验展示：当所有前台线程都结束后会自动关闭后台线程，无论后台线程是否执行完。
1. 点击`前台线程先结束`按钮
2. 步骤1后立即点击退出按钮
3. 观察 Visual Studio 的 output 窗口
4. 分析 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第216行 `btn3_Click` 函数的代码

分析为什么会出现观察到的结果。


### 1.4 无后台线程: 将1.3中的后台线程都改为前台线程

本实验展示：将1.3中的后台线程都改为前台线程后，即便先前的前台线程都结束后也不会会自动关闭`后台线程改为前台线程`，直到等待`后台线程改为前台线程`执行完。
1. 点击`前台线程先结束`按钮
2. 步骤1后立即点击退出按钮
3. 观察 Visual Studio 的 output 窗口
4. 分析 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第241行 `btn4_Click()` 函数的代码

分析为什么会出现观察到的结果。


### 1.5 线程方法:Join

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第283行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 多次按快捷键 F10 逐行追踪代码的运行直到退出 `btn5_Click` 函数
4. 按快捷键 F5 直到返回界面

问题：为什么 `btn5_Click` 函数中的 `joinThread` 线程最后退出？


### 1.6 同步调用

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第315行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 按快捷键 F5 直到返回界面

问题：运行时为什么界面会被锁死，直到调用结束后才在界面上显示全部中间结果？


### 1.7 异步调用

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第336行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 按快捷键 F5 直到返回界面，观察界面是否锁死
4. 参照第354行将第353行 `action.BeginInvoke(...)` 改为 `action.Invoke(...)` 后再运行一遍，观察界面是否锁死

问题：运行时为什么改为`Invoke`界面会被锁死？


### 1.8 线程采用异步回调的方法进行同步

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第364行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 按快捷键 F5 直到返回界面，观察界面是否锁死

问题：运行时为什么界面不会被锁死？


### 1.9 AutoResetEvent

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第438行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 按快捷键 F5 直到返回界面，观察界面中的输出
4. 屏蔽第408行的`Thread.Sleep(2000);`, 重新上述第1步到第3步，观察界面输出的变化。
5. 撤回第4步的修改
6. 屏蔽第416行的`Thread.Sleep(2000);`, 重新前面第1步到第3步，观察界面输出的变化。
7. 撤回第6步的修改

分析：导致界面输出发生变化的原因及背后的原理。


### 1.10 ManualResetEvent WaitOne

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第604行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 按快捷键 F5 直到返回界面，观察界面中的输出

问题：第537行及第542行的`manualResetEvent.WaitOne();`各自对应的是哪行的`manualResetEvent.Set()`?


### 1.11 ManualResetEvent WaitAny

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第613行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 按快捷键 F5 直到返回界面，观察界面中的输出
4. 屏蔽第470行的`Thread.Sleep(2000);`, 重新上述第1步到第3步，观察界面输出的变化。
5. 撤回第4步的修改
6. 屏蔽第479行的`Thread.Sleep(3000);`, 重新前面第1步到第3步，观察界面输出的变化。
7. 撤回第6步的修改

分析：导致界面输出发生变化的原因及背后的原理。


### 1.12 生产者消费者

1. 在 wpfTest 的后台代码(code-behind) C3_SY1.xaml.cs 的第622行 `clearComments();` 处按快捷键 F9 设置断点
2. 运行 wpfTest 至第一步所设置的断点处
3. 按快捷键 F5 直到返回界面，观察界面中的输出

选做：给出一个完善该步实验的思路，以便更好地展示生产者消费者模型同步的原理。


## 2 线程间同步通信





