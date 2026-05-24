# C

中的 getmaxcolor()函数

> 原文:[https://www.geeksforgeeks.org/getmaxcolor-function-c/](https://www.geeksforgeeks.org/getmaxcolor-function-c/)

头文件 graphics.h 包含 **getmaxcolor()** 函数，返回当前图形模式和驱动的最大颜色值。由于颜色编号从零开始，当前图形模式和驱动程序可用的颜色总数为(getmaxcolor() + 1)。

**语法:**

```cpp
int getmaxcolor();

```

下面是 getmaxcolor()函数的实现。

```cpp
// C Implementation for getmaxcolor()
#include <graphics.h>
#include <stdio.h>

// driver code
int main()
{
    // gm is Graphics mode which is
    // a computer display mode that
    // generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // sprintf stands for “String print”.
    // Instead of printing on console, it
    // store output on char buffer which
    // are specified in sprintf
    sprintf(arr, "Maximum number of colors for "
                 "current graphics mode and "
               "driver = %d", getmaxcolor() + 1);

    // outtext function displays text
    // at current position.
    outtextxy(20, 100, arr);

    getch();

    // closegraph function closes the
    // graphics mode and deallocates
    // all memory allocated by
    // graphics system .
    closegraph();

    return 0;
}
```

输出: