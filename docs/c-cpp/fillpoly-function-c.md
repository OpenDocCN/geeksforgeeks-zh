# 在 C

中填充 poly()函数

> 原文:[https://www.geeksforgeeks.org/fillpoly-function-c/](https://www.geeksforgeeks.org/fillpoly-function-c/)

头文件 graphics.h 包含 **fillpoly()** 功能，用于绘制和填充多边形，即三角形、矩形、五边形、六边形等。它需要与 drawpoly()相同的参数。

**语法:**

```cpp
void fillpoly( int number, int *polypoints );

where,
number indicates (n + 1) number of points 
where, n is the number of vertices in a 
polygon. polypoints points to a sequence
of (n*2) integers.

```

示例:

```cpp
Input : arr[] = {320, 150, 400, 250,
                 250, 350, 320, 150};
Output : 

Input : arr[] = {120, 250, 400, 250, 400,
                350, 450, 200, 120, 250};
Output : 

```

**说明:**fill poly()的声明包含两个参数:number 表示(n + 1)个点数，其中 n 是多边形中的顶点数。第二个参数，即多点，指向一个(n * 2)整数序列。每对整数给出多边形上一个点的 x 和 y 坐标。我们指定(n + 1)个点，因为第一个点的坐标应该等于第(n + 1)个点才能画出完整的图形。

**示例 1:** 使用 fillpoly 绘制三角形。
int arr[] = {320，150，400，250，250，350，320，150 }；

数组 *arr* 包含三角形的坐标，分别为(320，150)、(400，250)和(250，350)。请注意，数组中的最后一个点(320，150)与第一个点相同。

下面是 fillpoly()函数的实现。

```cpp
// C Implementation for fillpoly()
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

    // coordinates for polygon
    int arr[] = {320, 150, 400, 250, 
                250, 350, 320, 150};

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // fillpoly function
    fillpoly(4, arr);

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

**注意:** fillpoly()使用当前填充图案和颜色进行填充，可以使用 setfillstyle 进行更改。

下面是使用 setfillstyle()填充多边形的程序。

```cpp
// C Implementation for fillpoly()
// using setfillstyle()
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

    // coordinates of polygon
    int arr[] = {320, 150, 400, 250, 
                 250, 350, 320, 150};

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // setfillstyle function sets the
    // current fill pattern and fill color.
    setfillstyle(XHATCH_FILL, RED);

    // fillpoly function
    fillpoly(4, arr);

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