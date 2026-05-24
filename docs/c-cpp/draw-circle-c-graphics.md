# 在 C 图形中画圆

> 原文:[https://www.geeksforgeeks.org/draw-circle-c-graphics/](https://www.geeksforgeeks.org/draw-circle-c-graphics/)

头文件 graphics.h 包含**圆()**函数，该函数绘制一个圆心在(x，y)且半径给定的圆。

**语法:**

```cpp
circle(x, y, radius);

where,
(x, y) is center of the circle.
'radius' is the Radius of the circle.

```

**示例:**

```cpp
Input : x = 250, y = 200, radius = 50
Output : 

Input : x = 300, y = 150, radius = 90
Output : 

```

下面是用 C 画圆的实现:

```cpp
// C Implementation for drawing circle
#include <graphics.h>

//driver code
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

    // circle function
    circle(250, 200, 50);

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