# C

中的 outtextxy()函数

> 原文:[https://www.geeksforgeeks.org/outtextxy-function-c/](https://www.geeksforgeeks.org/outtextxy-function-c/)

头文件 graphics.h 包含**outextxy()**函数，该函数在屏幕上的指定点(x，y)显示文本或字符串。

**语法:**

```cpp
void outtextxy(int x, int y, char *string);

where, x, y are coordinates of 
the point and, third argument contains
the address of string to be displayed.

```

**示例:**

```cpp
Input : x = 200, y = 150, 
        string = "Hello Geek, Have a good day !"
Output : 

Input : x = 150, y = 250, 
        string = "GeeksforGeeks is the best !"
Output : 

```

下面是 outtextxy()函数的实现:

```cpp
// C Implementation for outtextxy()
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

    // outtextxy function
    outtextxy(200, 150, "Hello Geek, Have a good day !");

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