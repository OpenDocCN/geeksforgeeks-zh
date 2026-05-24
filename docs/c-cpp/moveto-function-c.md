# C

中的 moveto()功能

> 原文:[https://www.geeksforgeeks.org/moveto-function-c/](https://www.geeksforgeeks.org/moveto-function-c/)

头文件 graphics.h 包含 **moveto()** 函数，该函数将当前位置更改为(x，y)

**语法:**

```cpp
 void moveto(int x, int y);

```

**示例:**

```cpp
Input : x = 70, y = 40
Output : 

Input : x = 50, y = 80
Output : 

```

下面是 moveto()函数的实现:

```cpp
// C Implementation for moveto()
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
    sprintf(arr, "X = %d, Y = %d", getx(),
                                 gety());

    // outtext function displays text at
    // current position.
    outtext(arr);

    // moveto function
    moveto(70, 40);

    // The function getx returns the X
    // coordinate of the current position.
    // The function gety returns the y
    // coordinate of current position.
    sprintf(arr, "X = %d, Y = %d", getx(), 
                                 gety());

    outtext(arr);

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