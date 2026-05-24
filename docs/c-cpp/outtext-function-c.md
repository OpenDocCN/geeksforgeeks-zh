# C

中的 outtext()函数

> 原文:[https://www.geeksforgeeks.org/outtext-function-c/](https://www.geeksforgeeks.org/outtext-function-c/)

头文件 graphics.h 包含 **outtext()** 功能，在当前位置显示文本。

**语法:**

```cpp
void outtext(char *string);

```

**示例:**

```cpp
Input : string = "Hello Geek, Have a good day !"
Output : 

Input : string = "GeeksforGeeks is the best !"
Output :  

```

**注意:**在图形模式下工作时，不要使用 printf 等文本模式功能。使用 outtext 时，确保文本不会超出屏幕。

下面是 outtext()函数的实现:

```cpp
// C Implementation for outtext()
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

    // outtext function
    outtext("Hello Geek, Have a good day !");

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