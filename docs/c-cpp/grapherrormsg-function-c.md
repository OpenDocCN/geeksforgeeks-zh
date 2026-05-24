# C

中的 grapherrormsg()函数

> 原文:[https://www.geeksforgeeks.org/grapherrormsg-function-c/](https://www.geeksforgeeks.org/grapherrormsg-function-c/)

头文件 graphics.h 包含 **grapherrormsg()** 函数，该函数返回一个错误消息字符串。
**语法:**

```cpp
char *grapherrormsg( int errorcode );
where,
errorcode: code for the respective error

```

**graph errormsg()的说明:**在下面的程序中，gd = DETECT 没有被写入，因此程序必须抛出一个错误。

下面是 C 语言中 grapherrormsg()函数的实现

```cpp
// C Implementation for grapherrormsg()
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
    int gd, gm, errorcode;

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // graphresult returns the error code
    // for the last graphics operation
    // that reported an error and resets
    // the error level to grOk.
    errorcode = graphresult();

    if( errorcode != grOk)
    {
      printf("Graphics error: %s\n", 
             grapherrormsg(errorcode));

      printf("Press any key to exit.");
      getch();
      exit(1);
    }

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