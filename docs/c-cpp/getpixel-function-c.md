# C

中的 getpixel()函数

> 原文:[https://www.geeksforgeeks.org/getpixel-function-c/](https://www.geeksforgeeks.org/getpixel-function-c/)

头文件 graphics.h 包含 **getpixel()** 函数，该函数返回出现在位置(x，y)的像素的颜色。

**语法:**

```cpp
int getpixel(int x, int y);

```

**注意:**默认屏幕为黑色，因此(0，0)处的像素颜色为黑色。

下面是 getpixel()函数的实现。

```cpp
// C Implementation for getpixel()
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
    int gd = DETECT, gm, color;
    char arr[50];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // getpixel function
    color = getpixel(0, 0);

    // sprintf stands for “String print”.
    // Instead of printing on console,
    // it store output on char buffer
    // which are specified in sprintf
    sprintf(arr, "color of pixel at (0,0) = %d",
                                       color);

    // outtext function displays text
    // at current position.
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

**说明:**由于屏幕上什么都没有画，默认屏幕是黑色，因此(0，0)像素的颜色是黑色，因为 0 表示黑色。