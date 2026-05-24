# C

中的 getmaxx()函数

> 原文:[https://www.geeksforgeeks.org/getmaxx-function-c/](https://www.geeksforgeeks.org/getmaxx-function-c/)

头文件 graphics.h 包含 **getmaxx()** 函数，该函数返回当前图形模式和驱动程序的最大 X 坐标。
**语法:**

```cpp
int getmaxx();

```

下面是 getmaxx()函数的实现:

```cpp
// C Implementation for getmaxx()
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
    sprintf(arr, "Maximum X coordinate for current "
        "graphics mode And driver = %d", getmaxx());

    // outtext function displays text at
    // current position.
    outtext(arr);

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