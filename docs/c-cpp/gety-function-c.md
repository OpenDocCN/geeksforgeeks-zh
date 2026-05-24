# gety()函数在 C

中

> 原文:[https://www.geeksforgeeks.org/gety-function-c/](https://www.geeksforgeeks.org/gety-function-c/)

头文件 graphics.h 包含 **gety()** 函数，返回当前位置的 Y 坐标。
**语法:**

```cpp
int gety();

```

**示例:**

**说明:**最初，当前位置的 Y 坐标为 0。使用 *moveto()* 功能移动坐标时，Y 坐标变为 50。

下面是 gety()函数的实现:

```cpp
// C Implementation for gety()
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
    sprintf(arr, "Current position of y = %d", 
                                     gety());

    // outtext function displays text at
    // current position.
    outtext(arr);

    // moveto function
    moveto(80, 50);
    sprintf(arr, "Current position of y = %d",
                                     gety());

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