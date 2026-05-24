# C

中的 fillellipse()函数

> 原文:[https://www.geeksforgeeks.org/fillellipse-function-c/](https://www.geeksforgeeks.org/fillellipse-function-c/)

头文件 graphics.h 包含**filellipse()**函数，该函数绘制并填充一个以(x，y)和(x_radius，y_radius)为椭圆的 x 和 y 半径的椭圆。
**语法:**

```cpp
void fillellipse(int x, int y, int x_radius,
                              int y_radius);

where,
(x, y) is center of the ellipse.
(x_radius, y_radius) are x and y 
radius of ellipse.

```

**示例:**

```cpp
Input : x = 200, y = 200,
        x_radius = 50, y_radius = 90
Output : 

Input : x = 300, y = 250,
        x_radius = 100, y_radius = 70
Output : 

```

下面是 fillellipse()函数的实现:

```cpp
// C Implementation for fillellipse()
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

    // fillellipse function
    fillellipse(200, 200, 50, 90);

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