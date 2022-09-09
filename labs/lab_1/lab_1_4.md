# Implement a custom control class

�ο���ҳ��
<https://docs.microsoft.com/en-us/windows/apps/winui/winui3/xaml-templated-controls-cppwinrt-winui-3>

***

��ʵ����[ʵ�� 1_2](lab_1_2.md)�������ɵ� winuiTest ��Ŀ�Ļ���������
һ����ť��һ����ǩ�࣬���б�ǩ�ఴ�ղο���ҳ�����ɡ�����������ղο���ҳ��
��Ҫע�����µط��� 
1. namespace �ĸı䣬�ο���ҳ�� namespace �� BgLabelControlApp������������
winuiTest �� namespace �� winuiTest

2. BgLabelControl �Ĺ��캯���� DefailtStyleKey �е��ַ���Ҫ����Ӧ����,
�� BgLabelControlApp ��Ϊ winuiTest:

```cpp
BgLabelControl() { DefaultStyleKey(winrt::box_value(L"BgLabelControlApp.BgLabelControl")); }
```

3. ע�� Design the default style for BgLabelControl ��һ�ڣ����
��ӿγ���վ�Ĳֿ� winuiTest �п����Ļ�������Ҫ���ļ��� "Themes" ��������
����Ŀ�У���ע�⽫��Ӧ�� local �Ķ����������޸ģ�

```xml
xmlns:local="using:winuiTest"
```

4. �� `pch.h` ������

```cpp
#include <winrt/Windows.UI.Xaml.Interop.h>
```
