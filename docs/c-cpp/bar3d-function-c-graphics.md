# C 图形中的 bar3d()函数

> 原文:[https://www.geeksforgeeks.org/bar3d-function-c-graphics/](https://www.geeksforgeeks.org/bar3d-function-c-graphics/)

头文件 graphics.h 包含 **bar3d()** 函数，用于绘制二维矩形填充条。绘制条形需要条形左上角和右下角的坐标。
**语法:**

```cpp
void bar3d(int left, int top, int right, 
    int bottom, int depth, int topflag);

where,
left specifies the X-coordinate of top left corner,
top specifies the Y-coordinate of top left corner, 
right specifies the X-coordinate of right bottom corner, 
bottom specifies the Y-coordinate of right bottom corner, 
depth specifies the depth of bar in pixels, 
topflag determines whether a 3 dimensional top is put on 
the bar or not ( if it is non-zero then it is put otherwise not ).

```

**示例:**

```cpp
Input : left = 150, top = 250,
        right = 190, bottom = 350,
        depth = 20, topflag = 1

        left = 220, top = 150,
        right = 260, bottom = 350, 
        depth = 20, topflag = 0

        left = 290, top = 200, 
        right = 330, bottom = 350, 
        depth = 20, topflag = 1
Output : 

```

下面是 bar3d()函数的实现:

```cpp
// C Implementation for bar3d() function
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

    // location of sides
    int left, top, right, bottom;

    // depth of the bar
    int depth;

    // top flag denotes top line.
    int topflag;

    // left, top, right, bottom,
    // depth, topflag location's
    bar3d(left = 150, top = 250,
    right = 190, bottom = 350,
    depth = 20, topflag = 1);

    bar3d(left = 220, top = 150,
    right = 260, bottom = 350,
    depth = 20, topflag = 0);

    bar3d(left = 290, top = 200,
    right = 330, bottom = 350,
    depth = 20, topflag = 1);

    // y axis line
    line(100, 50, 100, 350);

    // x axis line
    line(100, 350, 400, 350);

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