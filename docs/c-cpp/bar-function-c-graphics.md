# C 图形中的 bar()函数

> 原文:[https://www.geeksforgeeks.org/bar-function-c-graphics/](https://www.geeksforgeeks.org/bar-function-c-graphics/)

头文件 graphics.h 包含**条()**函数，用于绘制二维矩形填充条。
**语法:**

```cpp
void bar(int left, int top, int right, int bottom);

where,
left specifies the X-coordinate of top left corner,
top specifies the Y-coordinate of top left corner,
right specifies the X-coordinate of right bottom corner,
bottom specifies the Y-coordinate of right bottom corner.

```

**示例:**

```cpp
Input : left = 150, top = 150, 
        right = 190, bottom = 350

        left = 220, top = 250, 
        right = 260, bottom = 350

        left = 290, top = 200, 
        right = 330, bottom = 350
Output : 

Input : left = 150, top = 250,
        right = 190, bottom = 350

        left = 220, top = 150, 
        right = 260, bottom = 350

        left = 290, top = 200,
        right = 330, bottom = 350
Output : 

```

下面是 bar()函数的实现。

```cpp
// C implementation of bar() function
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

    // left, top, right, bottom denotes
    // location of rectangular bar
    bar(left = 150, top = 150, 
    right = 190, bottom = 350);

    bar(left = 220, top = 250,
    right = 260, bottom = 350);

    bar(left = 290, top = 200,
    right = 330, bottom = 350);

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