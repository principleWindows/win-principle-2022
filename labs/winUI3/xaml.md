# Templated XAML controls

Please refer to [Templated XAML controls for UWP and WinUI 3 apps with C++/WinRT](https://docs.microsoft.com/en-us/windows/apps/winui/winui3/xaml-templated-controls-cppwinrt-winui3),
which describes the same scenario as the article 
[XAML custom (templated) controls with C++/WinRT](https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/xaml-cust-ctrl) 
but has been adapted to use WinUI 3.

***

Templated controls inherit from Microsoft.UI.Xaml.Controls.Control and 
have visual structure and visual behavior that can be customized using 
XAML control templates.

The XAML classes for WinUI 3 library are in Microsoft.UI.Xaml namespaces. 
This is what distinguishes them as WinUI controls as opposed to UWP XAML 
controls, which are defined in Windows.UI.XAML namespaces.
Microsoft is currently in the progress of breaking out the entire 
interface layer that contains the modern Windows controls and styles from 
the operating system into a separate WinUI 3 framework that will ship 
later this year.

The Nuget package [Microsoft.UI.Xaml](https://www.nuget.org/packages/Microsoft.UI.Xaml)
provides backward-compatible versions of Windows UI features including UWP 
XAML controls, and Fluent styles and materials. It is part of the 
Windows UI Library. <font size=5>(�༴ Microsoft.UI.Xaml �������ݵ��ֶ�)</font>



 **XAML ��������?**

XAML ʹ�ý��������ҵ���߼����Է��룬����Ա��дҵ���߼����룬
ǰ̨�����������������Ա���� XAML �����С�

�� C++ winUI ������, APP �ļ��ǳ������ڡ�
![App](pix/app.PNG)

1. ��ǩ����Ԫ��(Object Elements)<br>
ÿ����ǩ��Ӧһ������Ԫ�أ��������������Ϊĳ�����ʵ����
����Ĵ������һ����ǩ����Ԫ�أ�����ʱ�ᱻ����Ϊһ�� 
\:\:winrt\:\:Microsoft\:\:UI\:\:Xaml\:\:Controls\:\:Button ����ʵ����
```cpp
<Button x:Name="myButton" Click="myButton_Click">Click Me</Button>
```



