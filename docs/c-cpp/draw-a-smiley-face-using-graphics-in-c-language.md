# 用 C 语言的 Graphics 画一个笑脸

> 原文:[https://www . geesforgeks . org/用 c 语言图形绘制笑脸/](https://www.geeksforgeeks.org/draw-a-smiley-face-using-graphics-in-c-language/)

**先决条件:**[graphics.h](https://www.geeksforgeeks.org/add-graphics-h-c-library-gcc-compiler-linux/)[如何在 CodeBlocks 中包含 graphics . h？](https://www.geeksforgeeks.org/include-graphics-h-codeblocks/)
任务是编写一个 [C 程序](https://www.geeksforgeeks.org/c-programming-language/)用 C 中的图形画一个笑脸
要运行这个程序，我们有下面包含的头文件:

```cpp
#include <graphic.h>
```

**方法:**我们将借助以下功能创建一个笑脸:

1.  [**【filellipse(int x，int y，int x_radius，int y_radius)**](https://www.geeksforgeeks.org/fillellipse-function-c/)**:**graphics . h 头文件中的一个函数，它绘制并填充一个以(x，y)为中心，以(x_radius，y _ radius)为椭圆的 x 和 y 半径的椭圆。
2.  [**椭圆(int x，int y，int stangle，int endangle，int xradius，int yradius)**](https://www.geeksforgeeks.org/draw-ellipse-c-graphics/) **:** 一个来自 graphics.h 头文件的函数，用来绘制椭圆(X，Y)的是椭圆中心的坐标，stangle 是起始角，end 角是结束角，而第五和第六个参数指定了椭圆的 X 和 Y 半径。
3.  [**【setcolor(n)**](https://www.geeksforgeeks.org/setcolor-function-c/)**:**一个从 graphics.h 头文件中设置指针(光标)颜色的函数。
4.  [**【setfillstyle()**](https://www.geeksforgeeks.org/setfillstyle-floodfill-c/)**:**graphics . h 头文件中设置当前填充模式和填充颜色的函数。
5.  [**【漫填】()**](https://www.geeksforgeeks.org/setfillstyle-floodfill-c/)**:**graphics . h 头文件中用于填充封闭区域的函数。

下面是用 C 语言图形绘制笑脸的实现:

## C

```cpp
// C program to create a smiley face
#include <conio.h>
#include <dos.h>
#include <graphics.h>
#include <stdio.h>

// Driver Code
int main()
{

    // Initialize graphic driver
    int gr = DETECT, gm;

    // Initialize graphics mode by passing
    // three arguments to initgraph function

    // &gdriver is the address of gdriver
    // variable, &gmode is the address of
    // gmode and  "C:\\Turboc3\\BGI" is the
    // directory path where BGI files
    // are stored
    initgraph(&gr, &gm, "C:\\Turboc3\\BGI");

    // Set color of smiley to yellow
    setcolor(YELLOW);

    // creating circle and fill it with
    // yellow color using floodfill.
    circle(300, 100, 40);
    setfillstyle(SOLID_FILL, YELLOW);
    floodfill(300, 100, YELLOW);

    // Set color of background to black
    setcolor(BLACK);
    setfillstyle(SOLID_FILL, BLACK);

    // Use fill ellipse for creating eyes
    fillellipse(310, 85, 2, 6);
    fillellipse(290, 85, 2, 6);

    // Use ellipse for creating mouth
    ellipse(300, 100, 205, 335, 20, 9);
    ellipse(300, 100, 205, 335, 20, 10);
    ellipse(300, 100, 205, 335, 20, 11);

    getch();

    // closegraph function closes the
    // graphics mode and deallocates
    // all memory allocated by
    // graphics system
    closegraph();

    return 0;
}
```

**输出:**
下面是上面程序的输出:

![Smiley Image](img/c58f57e685b57de4812056336a854243.png)