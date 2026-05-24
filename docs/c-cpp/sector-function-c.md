# C

中的扇形()功能

> 原文:[https://www.geeksforgeeks.org/sector-function-c/](https://www.geeksforgeeks.org/sector-function-c/)

头文件 graphics.h 包含 sector()函数，该函数以(x，y)为中心，以(s_angle，e_angle)为起始和结束角度，以(x_radius，y_radius)为扇区的 x 和 y 半径，绘制并填充一个椭圆形饼图切片。
**语法:**

```cpp
void sector(int x, int y, int s_angle, 
           int e_angle, int x_radius, 
                        int y_radius);

where,
(x, y) is center of the sector.
(s_angle, e_angle) are starting 
and ending angles.
(x_radius, y_radius) are x and y
radius of sector.

```

**示例:**

```cpp
Input : x = 200, y = 200, s_angle = 0,
         e_angle = 150, x_radius = 50, 
         y_radius = 65
Output : 

Input : x = 200, y = 200, s_angle = 30, 
        e_angle = 120, x_radius = 90, 
        y_radius = 85 
Output : 

```

下面是扇区()函数的实现:

```cpp
// C Implementation for sector()
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

    // sector function
    sector(200, 200, 0, 150, 50, 65);

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