# 如何在 C 中找到分割错误& C++？(使用 GDB)

> 原文:[https://www . geesforgeks . org/how-find-segmentation-error-in-c-using-gdb/](https://www.geeksforgeeks.org/how-to-find-segmentation-error-in-c-c-using-gdb/)

什么是[分段错误](https://www.geeksforgeeks.org/core-dump-segmentation-fault-c-cpp/)？
–这是由于内存访问冲突导致的运行时错误。将 Eg :-Stackoverflow 改为违例等..
我们在 c++/c 中使用指针进行运算时经常会遇到这个问题。
在这个例子中，我们将看到如何在程序中找到分段错误。我们将找到导致分段错误的线。
注意:-我在这个演示中使用了 Linux 发行版–Ubuntu。
所以，考虑下面的 C++ 代码片段。

```cpp
// Segmentation Error Demonstration
// Author - Rohan Prasad
#include <iostream>
using namespace std;

int main()
{
    int* p = NULL;

    // This lines cause the segmentation 
    // error because of accessing the 
    // unknown memory location.
    *p = 1;

    cout << *p;
    return 0;
}
```

 **如何使用 gdb 找到那个错误？**
假设你的文件名保存为 **Program1.cpp** 。前往您的终端(在该程序可用的目录中)

第一步:编译它。
`$ gcc -g Program1.cpp`(以我为例)。
第二步:运行。
`$ ./a.out`(它是对象文件)
如果它显示分段故障(核心被转储)，则按照以下步骤操作。
第三步:调试
`$ gdb ./a.out core`
你的输出会看起来像这样:【————————————————————————————】

————————————————————————————————————
然后只需键入 r 并按回车键。
输出会是这样的，显示错误的陈述。
————————————————————————————————
T0】

程序接收信号，分段故障。
Sege . CPP 处 main()中的 0x 0000555555547 de:8
8 * p = 1；
(gdb)

———————————————————
现在你已经得到了导致分段错误的线。
退出调试器并纠正程序。
退出类型退出并按回车键。
————————————————————————————————
 `(gdb) quit
A debugging session is active.`

`Inferior 1 [process 3617] will be killed.`

`Quit anyway? (y or n) y`

————————————————————————————————————————
所以，哇你解决了折磨头部的分割故障。