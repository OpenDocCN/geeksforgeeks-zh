# C

中的 textheight()函数

> 原文:[https://www.geeksforgeeks.org/textheight-function-c/](https://www.geeksforgeeks.org/textheight-function-c/)

头文件 graphics.h 包含 **textheight()** 函数，以像素为单位返回输入字符串的高度。
**语法:**

```cpp
int textheight(char *string);

```

**示例:**

```cpp
Input : string = "Hello Geek ! Have a good day."
Output : 

```

下面是 textheight()函数的实现。

```cpp
// C Implementation for textheight()
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
    int gd = DETECT, gm, color, height;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // textheight function
    height = textheight("Hello Geek ! Have a good day.");

    //sprintf stands for “String print”.
    //Instead of printing on console,
    //it store output on char buffer
    //which are specified in sprintf
    sprintf(arr, "Textheight is = %d", height);

    //outtext function displays text
    //at current position.
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