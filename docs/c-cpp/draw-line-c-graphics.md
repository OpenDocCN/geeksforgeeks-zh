# 在 C++ 图形中画线

> 原文:[https://www.geeksforgeeks.org/draw-line-c-graphics/](https://www.geeksforgeeks.org/draw-line-c-graphics/)

**graphics.h** 库用于包含和方便程序中的图形化操作。graphics.h 函数可以用来绘制不同的形状，以不同的字体显示文本，改变颜色等等。利用图形的功能，你可以制作图形程序、动画、项目和游戏。你可以画圆、线、矩形、条和许多其他几何图形。您可以使用可用的功能更改它们的颜色并填充它们。

**示例:**

```cpp
For line 1, Input : x1 = 150, y1 = 150, x2 = 450, y2 = 150
For line 2, Input : x1 = 150, y1 = 200, x2 = 450, y2 = 200
For line 2, Input : x1 = 150, y1 = 250, x2 = 450, y2 = 250
Output :

```

**说明:**头文件 graphics.h 包含如下所述的 line()函数:

声明:**空行(int x1，int y1，int x2，int y2)；**

直线函数用于绘制从点(x1，y1)到点(x2，y2)的直线，即(x1，y1)和(x2，y2)是直线的端点。下面给出的代码画了一条线。

```cpp
// C++ Implementation for drawing line
#include <graphics.h>

// driver code
int main()
{
    // gm is Graphics mode which is a computer display
    // mode that generates image using pixels.
    // DETECT is a macro defined in "graphics.h" header file
    int gd = DETECT, gm;

    // initgraph initializes the graphics system
    // by loading a graphics driver from disk
    initgraph(&gd, &gm, "");

    // line for x1, y1, x2, y2
    line(150, 150, 450, 150);

    // line for x1, y1, x2, y2
    line(150, 200, 450, 200);

    // line for x1, y1, x2, y2
    line(150, 250, 450, 250);

    getch();

    // closegraph function closes the graphics
    // mode and deallocates all memory allocated
    // by graphics system .
    closegraph();
}
```

输出: