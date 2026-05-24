# C

中的 textwidth()函数

> 原文:[https://www.geeksforgeeks.org/textwidth-function-c/](https://www.geeksforgeeks.org/textwidth-function-c/)

头文件 graphics.h 包含 **textwidth ()** 函数，以像素为单位返回输入字符串的宽度。
**语法:**

```cpp
int textwidth(char *string);

```

**示例:**

```cpp
Input : string = "Hello Geek ! Have a good day."
Output : 

```

下面是 textwidth()函数的实现。

```cpp
// C Implementation for textwidth()
#include <graphics.h>
#include <stdio.h>

//driver code
int main()
{
    // gm is Graphics mode which is
    // a computer display mode that
    // generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm, color, width;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // textwidth function
    width = textwidth("Hello Geek ! Have a good day.");

    //sprintf stands for “String print”.
    //Instead of printing on console,
    //it store output on char buffer
    //which are specified in sprintf
    sprintf(arr, "Textwidth is = %d", width);

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