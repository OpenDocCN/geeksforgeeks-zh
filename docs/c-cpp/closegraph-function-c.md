# C

中的 closegraph()函数

> 原文:[https://www.geeksforgeeks.org/closegraph-function-c/](https://www.geeksforgeeks.org/closegraph-function-c/)

头文件 graphics.h 包含 **closegraph()** 函数，该函数关闭图形模式，释放图形系统分配的所有内存，并将屏幕恢复到调用 initgraph 之前的模式。

**语法:**

```cpp
void closegraph();

```

下面是 c 语言中 closegraph()的实现。

```cpp
// C Implementation for closegraph()
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

    // outtext function displays
    // text at current position.
    outtext("Press any key to close"
           " the graphics mode !!");

    getch();

    // closegraph function closes the
    // graphics mode and deallocates
    // all memory allocated by
    // graphics system .
    closegraph();

    return 0;
}
```

**输出:**

**注意:**执行程序时，输出窗口如上图所示。按任意键，closegraph()关闭图形模式。