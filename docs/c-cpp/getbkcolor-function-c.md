# 在 C

中获取 bkcolor()函数

> 原文:[https://www.geeksforgeeks.org/getbkcolor-function-c/](https://www.geeksforgeeks.org/getbkcolor-function-c/)

头文件 graphics.h 包含 **getbkcolor()** 函数，返回当前背景颜色。

**语法:**

```cpp
int getbkcolor();

```

由于 getbkcolor()返回一个对应于背景颜色的整数值，所以下面是 color 值的表格。
**颜色表:**

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

**背景色为黑色时:**

```cpp
// C Implementation for getbkcolor function
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
    int gd = DETECT, gm;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // sprintf stands for “String print”.
    // Instead of printing on console, it
    // store output on char buffer which
    // are specified in sprintf
    sprintf(arr, "Current background color = %d",
                                 getbkcolor());

    // outtext function displays text
    // at current position.
    outtextxy(10, 10, arr);

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

**当背景颜色不是黑色时:**

```cpp
// C Implementation for getbkcolor function
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
    int gd = DETECT, gm;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // set background color as RED
    setbkcolor(RED);

    // sprintf stands for “String print”.
    // Instead of printing on console, it
    // store output on char buffer which
    // are specified in sprintf
    sprintf(arr, "Current background color = %d", 
                                 getbkcolor());

    // outtext function displays text
    // at current position.
    outtextxy(10, 10, arr);

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