# C

中的 getarcoords()函数

> 原文:[https://www.geeksforgeeks.org/getarcoords-function-c/](https://www.geeksforgeeks.org/getarcoords-function-c/)

头文件 graphics.h 包含 **getarccoords()** 函数，用于获取最近绘制的圆弧的坐标。 **arccoordstype** 是一个预定义的结构，定义如下:

**语法:**

```cpp
struct arccoordstype
{
   // center point of arc
   int x, y; 

   // start position                
   int xstart, ystart;

   // end position        
   int xend, yend;    
};

```

**注意:【arccoordstype 类型的结构变量的地址被传递给函数 getarccoords。**

**语法:**

```cpp
void getarccoords(struct arccoordstype *var);

```

**示例:**

```cpp
Input : x = 250, y = 200, s_angle = 0 ,
        e_angle = 90, radius = 100
Output : 

```

下面是 getarccoords()函数的实现

```cpp
// C Implementation for getarccoords()
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

    // p is structure variable
    // of type arccoordstype
    struct arccoordstype p;
    char arr[100];

    // initgraph initializes the
    // graphics system by loading a
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // arc function is used to draw an 
    // arc the first 2 arguments are 
    // center of arc  3rd and 4th 
    // arguments are starting and  
    // ending angles. Last argument 
    // is the radius.
    arc(250, 200, 0, 90, 100);

    // getarccoords function which takes
    // address of a structure variable of
    // type arccoordstype as an argument.
    getarccoords(&p);

    // sprintf stands for “String print”.
    // Instead of printing on console, it
    // store output on char buffer which
    // are specified in sprintf
    sprintf(arr, "(%d, %d)", p.xstart, 
                             p.ystart);

    // outtext function displays text
    // at current position.
    outtextxy(360, 195, arr);

    sprintf(arr, "(%d, %d)", p.xend, 
                            p.yend);

    outtextxy(245, 85, arr);

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