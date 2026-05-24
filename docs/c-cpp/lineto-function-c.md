# C

中的 lineto()函数

> 原文:[https://www.geeksforgeeks.org/lineto-function-c/](https://www.geeksforgeeks.org/lineto-function-c/)

头文件 graphics.h 包含 **lineto()** 函数，该函数绘制一条从当前位置到点(x，y)的直线。
**注意:**使用 **getx()** 和 **gety()** 获取当前位置。

**语法:**

```cpp
lineto(int x, int y);

where,
(x, y) are the coordinates upto which the
line will be drawn from previous point.

```

**情况 1 :** 当点的初始位置为(0，0)时

以下是初始位置在原点的 lineto()函数的实现:

```cpp
// C Implementation for lineto()
#include <graphics.h>

// driver code
int main()
{
    // gm is Graphics mode which is
    // a computer display mode that
    // generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm;

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // lineto function
    lineto(250, 100);

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

**情况 2 :** 当点的初始位置不是(0，0)时

下面是初始位置不是原点的 lineto()函数的实现:

```cpp
// C Implementation for lineto()
#include <graphics.h>

// driver code
int main()
{
    // gm is Graphics mode which is
    // a computer display mode that
    // generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm;

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // change initial position of point
    // with moveto function
    moveto(100, 100);

    // lineto function
    lineto(250, 100);

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