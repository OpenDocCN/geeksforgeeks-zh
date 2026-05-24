# 在 C

中设置颜色功能

> 原文:[https://www.geeksforgeeks.org/setcolor-function-c/](https://www.geeksforgeeks.org/setcolor-function-c/)

头文件 graphics.h 包含 **setcolor()** 功能，用于将当前绘图颜色设置为新颜色。
**语法:**

```cpp
void setcolor(int color);

```

**说明:**在图形中，每种颜色都被赋予一个数字。可用的颜色总数为 16 种。可用颜色的数量取决于当前图形模式和驱动程序。例如，setcolor(红色)或 setcolor(4)将当前绘图颜色更改为红色。请记住，默认的绘图颜色是白色。颜色表如下所示。

```cpp
COLOR               INT VALUES
-------------------------------
BLACK                   0
BLUE                    1
GREEN                   2
CYAN                    3   
RED                     4
MAGENTA                 5
BROWN                   6 
LIGHTGRAY               7 
DARKGRAY                8
LIGHTBLUE               9
LIGHTGREEN             10
LIGHTCYAN              11
LIGHTRED               12
LIGHTMAGENTA           13
YELLOW                 14
WHITE                  15

```

下面是 setcolor()函数的实现。

```cpp
// C Implementation for setcolor()
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

    // Draws circle in white color
    // center at (100, 100) and radius
    // as 50
    circle(100, 100, 50);

    // setcolor function
    setcolor(GREEN);

    // Draws circle in green color
    // center at (200, 200) and radius
    // as 50
    circle(200, 200, 50);

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