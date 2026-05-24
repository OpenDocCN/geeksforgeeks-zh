# C 中的弧线功能

> 原文:[https://www.geeksforgeeks.org/arc-function-c/](https://www.geeksforgeeks.org/arc-function-c/)

头文件 graphics.h 包含 **arc()** 函数，该函数绘制一个圆心在(x，y)且半径给定的圆弧。start_angle 是角度的起点，end_angle 是角度的终点。角度值可以从 0 度到 360 度变化。

**语法:**

```cpp
void arc(int x, int y, int start_angle,
            int end_angle, int radius);

where,
(x, y) is the center of the arc.
start_angle is the starting angle and 
end_angle is the ending angle.
'radius' is the Radius of the arc.

```

**示例:**

```cpp
Input : x=250, y=250, start_angle = 155, end_angle = 300, radius = 100
Output :

Input : x=250, y=250, start_angle = 0, end_angle = 300, radius = 100;
Output :

```

下面是 arc()函数的实现:

```cpp
// C implementation of arc function
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

    // location of the arc
    int x = 250;
    int y = 250;

    // starting angle and ending angle
    // of the arc
    int start_angle = 155;
    int end_angle = 300;

    // radius of the arc
    int radius = 100;

    // initgraph initializes the graphics system
    // by loading a graphics driver from disk
    initgraph(&gd, &gm, "");

    // arc function
    arc(x, y, start_angle, end_angle, radius);

    getch();

    // closegraph function closes the graphics
    // mode and deallocates all memory allocated
    // by graphics system
    closegraph();

    return 0;
}
```

输出: