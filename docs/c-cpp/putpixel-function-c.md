# 将 pixel()函数放入 C

> 原文:[https://www.geeksforgeeks.org/putpixel-function-c/](https://www.geeksforgeeks.org/putpixel-function-c/)

头文件 graphics.h 包含 **putpixel()** 函数，该函数在指定颜色的位置(x，y)绘制像素。
**语法:**

```cpp
void putpixel(int x, int y, int color);

where, 
(x, y) is the location at which pixel
is to be put , and color specifies 
the color of the pixel.

```

**说明:**使用 putpixel(50，40，RED)可以绘制(50，40)处的红色像素。putpixel()函数可用于使用各种算法绘制圆、线和椭圆。

下面是 putpixel()函数的实现。

```cpp
// C Implementation for putpixel()
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

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // putpixel function
    putpixel(85, 35, GREEN);
    putpixel(30, 40, RED);
    putpixel(115, 50, YELLOW);
    putpixel(135, 50, CYAN);
    putpixel(45, 60, BLUE);
    putpixel(20, 100, WHITE);
    putpixel(200, 100, LIGHTBLUE);
    putpixel(150, 100, LIGHTGREEN);
    putpixel(200, 50, YELLOW);
    putpixel(120, 70, RED);

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