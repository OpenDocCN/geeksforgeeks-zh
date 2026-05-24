# C

中的 linerel()函数

> 原文:[https://www.geeksforgeeks.org/linerel-function-c/](https://www.geeksforgeeks.org/linerel-function-c/)

头文件 graphics.h 包含 **linerel()** 函数，该函数绘制一条从当前位置(x_pos1，y_pos1)到与当前位置有相对距离(x，y)的点的直线，然后将当前位置前进(x，y)。
**注:**使用 **getx()** 和 **gety()** 查找当前位置。

**语法:**

```cpp
linerel(int x, int y);

The end position is calculated as :
x_pos2 = x_pos1 + x;
y_pos2 = y_pos1 + y;

```

**示例:**

```cpp
Input : x_pos1 = 0, y_pos1 =0, x = 200, y = 100
Output : 

Input : x_pos1 = 100, y_pos1 = 150, x = 150, y = 60
Output : 

```

**情况 1 :** 当前位置在原点即(0，0)
下面是 C 中 linerel()函数的实现:

```cpp
// C Implementation for linerel()
#include <graphics.h>
#include<stdio.h>

// driver code
int main()
{
    // gm is Graphics mode which is
    // a computer display mode that
    // generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // linerel function
    linerel(200, 100);

    // sprintf stands for “String print”.
    // Instead of printing on console,
    // it store output on char buffer
    // which are specified in sprintf
    sprintf(arr, "Current x position = %d and "
             "y position = %d", getx(), gety());

    // outtext function displays
    // text at current position.
    outtextxy(100, 150, arr);

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

**情况 2 :** 当前位置不是原点时，(100，150)。
下面是 linerel()函数在 C 语言中的实现:

```cpp
// C Implementation for linerel()
#include <graphics.h>
#include<stdio.h>

// driver code
int main()
{
    // gm is Graphics mode which is
    // a computer display mode that
    // generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // Change current position using
    // moveto function
    moveto(100, 150);

    // linerel function
    linerel(150, 60);

    // sprintf stands for “String print”.
    // Instead of printing on console,
    // it store output on char buffer
    // which are specified in sprintf
    sprintf(arr, "Current x position = %d and "
             "y position = %d", getx(), gety());

    // outtext function displays
    // text at current position.
    outtextxy(100, 150, arr);

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