# C

中的 cleardevice()功能

> 原文:[https://www.geeksforgeeks.org/cleardevice-function-c/](https://www.geeksforgeeks.org/cleardevice-function-c/)

头文件 graphics.h 包含 **cleardevice()** 功能，在图形模式下清除屏幕，并将当前位置设置为(0，0)。清除屏幕包括用当前背景色填充屏幕。

**语法:**

```cpp
void cleardevice();

```

下面是 cleardevice()在 C 语言中的实现:

```cpp
// C Implementation for cleardevice()
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

    // set the background colour as GREEN
    setbkcolor(GREEN);

    // outtext function displays
    // text at current position.
    outtext("Press any key to clear the screen.");

    getch();

    // cleardevice function
    cleardevice();

    outtext("Press any key to exit...");

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

```cpp
On executing the program, the output window looks like :

On pressing any key :

To exit, press any key.

```