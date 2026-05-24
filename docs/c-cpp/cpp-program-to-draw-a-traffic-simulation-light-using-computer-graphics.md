# C++ 程序使用计算机图形绘制红绿灯模拟图

> 原文:[https://www . geesforgeks . org/CPP-program-to-draw-a-traffic-simulation-light-use-computer-graphics/](https://www.geeksforgeeks.org/cpp-program-to-draw-a-traffic-simulation-light-using-computer-graphics/)

在计算机中， [graphics.h](https://www.geeksforgeeks.org/basic-graphic-programming-in-c/) 可以用来提供直接的函数来绘制不同的坐标，如圆形、矩形等。使用这些形状，可以绘制不同的对象。本文重点介绍如何在 [Turbo C++ ](https://www.geeksforgeeks.org/difference-between-turbo-c-and-dev-c/) 中进行红绿灯模拟。

**使用的功能:**

*   [**延时(N)**](https://www.geeksforgeeks.org/time-delay-c/)【T4:】用于保持同屏 **N** 毫秒。由于程序的执行太快，因此，为了观察程序，使用了延迟功能。
*   [**【setcolor(n)**](https://www.geeksforgeeks.org/setcolor-function-c/)**:此功能用于设置光标的颜色。这里 **N** 是在 graphics.h 头文件中预定义的颜色**
*   [**【settextstyle()/settext 狡辩()**](https://www.geeksforgeeks.org/settextstyle-function-c/) **:** 此功能用于文本指针的样式化目的。
*   [**矩形(x1，y1，x2，y2)**](https://www.geeksforgeeks.org/draw-rectangle-c-graphics/?ref=rp) **:** 这个函数用来画一个矩形，其中 x1，y1，和 x2，y2 是一条线的坐标。
*   [**圆(x，y，r)**](https://www.geeksforgeeks.org/draw-circle-c-graphics/) **:** 这是圆的表示，其中 x，y 是圆心的坐标，r 是圆的半径。

**进场:**

*   首先，使用函数 **initgraph()** 初始化图形模式。
*   使用 rectangle()函数创建一个矩形，并使用 **setcolor()** 函数填充两条线的中间部分。
*   绘制 3 个圆，并使用类似 **setcolor()** 、 **floodfill()** 和 **setfillstyle()** 的函数对其进行相应的颜色/样式设置。
*   重复这一过程，直到红绿灯没有完成。
*   中间使用**延迟()**功能，将屏幕保持在我们想要的位置。

以下是上述方法的程序:

## C++

```cpp
// C++ program for the above approach
#include <conio.h>
#include <dos.h>
#include <graphics.h>
#include <iostream.h>
#include <stdlib.h>

// Driver Code
void main()
{
    clrscr();
    int gd = DETECT, gm, midx, midy;

    // Passed three arguments to the
    // initgraph function to initialize
    // graphics mode
    initgraph(&gd, &gm, "C:\\TC\\BGI");

    midx = getmaxx() / 2;
    midy = getmaxy() / 2;

    // Set color of intro text as cyan
    setcolor(CYAN);

    // Below just styling the text
    settextstyle(TRIPLEX_FONT, HORIZ_DIR, 4);
    settextjustify(CENTER_TEXT, CENTER_TEXT);
    outtextxy(midx, midy - 10, "TRAFFIC LIGHT SIMULATION");
    outtextxy(midx, midy + 10, "PRESS ANY KEY TO START");
    getch();
    cleardevice();
    setcolor(WHITE);
    settextstyle(DEFAULT_FONT, HORIZ_DIR, 1);

    // rectangle lines
    rectangle(midx - 30, midy - 80, midx + 30, midy + 80);

    // Circle for red light
    circle(midx, midy - 50, 22);
    setfillstyle(SOLID_FILL, RED);
    floodfill(midx, midy - 50, 22);
    setcolor(BLUE);

    // Text inside red light
    outtextxy(midx, midy - 50, "STOP");

    // Delay of 2 sec
    delay(2000);
    graphdefaults();
    cleardevice();

    setcolor(WHITE);

    // Drawing lines of  rectangle
    // for  traffic light
    rectangle(midx - 30, midy - 80,
              midx + 30, midy + 80);

    // Drawing yellow circle for light
    circle(midx, midy - 50, 22);
    setfillstyle(SOLID_FILL, YELLOW);
    floodfill(midx, midy, WHITE);
    setcolor(BLUE);

    // Setting inner text to ready
    outtextxy(midx - 18, midy - 3, "READY");
    delay(2000);
    cleardevice();

    setcolor(WHITE);

    // Drawing lines of  rectangle
    // for  traffic light
    rectangle(midx - 30, midy - 80,
              midx + 30, midy + 80);

    // Circle for green light
    circle(midx, midy + 50, 22);
    setfillstyle(SOLID_FILL, GREEN);
    floodfill(midx, midy + 50, WHITE);
    setcolor(BLUE);

    // Setting inner text to GO
    outtextxy(midx - 7, midy + 48, "GO");
    setcolor(RED);
    settextstyle(TRIPLEX_FONT,
                 HORIZ_DIR, 4);

    outtextxy(midx - 150, midy + 100,
              "Brrrmmm");

    getch();
}
```

**输出:**

<video class="wp-video-shortcode" id="video-604763-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210511102935/hh.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210511102935/hh.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210511102935/hh.mp4)</video>