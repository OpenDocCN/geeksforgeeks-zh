# 在 C 图形中绘制矩形

> 原文:[https://www.geeksforgeeks.org/draw-rectangle-c-graphics/](https://www.geeksforgeeks.org/draw-rectangle-c-graphics/)

**矩形()**用于绘制矩形。绘制矩形需要左上角和右下角的坐标。左指定左上角的 X 坐标，上指定左上角的 Y 坐标，右指定右下角的 X 坐标，下指定右下角的 Y 坐标。
**语法:**

```cpp
rectangle(int left, int top, int right, int bottom);

```

**示例:**

```cpp
Input : left = 150, top = 250, right = 450, bottom = 350;
Output : 

Input : left = 150, top = 150, right = 450, bottom = 450;
Output : 

```

下面是矩形函数的实现:

```cpp
// C program to draw a rectangle
#include <graphics.h>

// Driver code
int main()
{
    // gm is Graphics mode which is a computer display
    // mode that generates image using pixels.
    // DETECT is a macro defined in "graphics.h" header file
    int gd = DETECT, gm;

    // location of left, top, right, bottom
    int left = 150, top = 150;
    int right = 450, bottom = 450;

    // initgraph initializes the graphics system
    // by loading a graphics driver from disk
    initgraph(&gd, &gm, "");

    // rectangle function
    rectangle(left, top, right, bottom);

    getch();

    // closegraph function closes the graphics
    // mode and deallocates all memory allocated
    // by graphics system .
    closegraph();

    return 0;
}
```

输出: