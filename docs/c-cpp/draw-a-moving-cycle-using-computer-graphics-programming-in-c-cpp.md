# 用 C/C++

中的计算机图形编程绘制一个移动的循环

> 原文:[https://www . geesforgeks . org/draw-a-move-cycle-use-computer-graphics-programming-in-c-CPP/](https://www.geeksforgeeks.org/draw-a-moving-cycle-using-computer-graphics-programming-in-c-cpp/)

在 [C 图形](https://www.geeksforgeeks.org/add-graphics-h-c-library-gcc-compiler-linux/)中， [graphics.h](https://www.geeksforgeeks.org/include-graphics-h-codeblocks/) 功能用于绘制不同的形状，如圆形、矩形等，以不同的格式(不同的字体和颜色)显示文本(任何消息)。通过使用 header graphics.h 中的功能，还可以制作程序、动画和不同的游戏。在这篇文章中，我们来讨论一下如何使用[图形](https://www.geeksforgeeks.org/applications-of-computer-graphics/)在 C 中绘制一个移动的循环。

**使用的功能:**

*   [**线(x1，y1，x2，y2)**](https://www.geeksforgeeks.org/draw-line-c-graphics/) **:** 是 graphics.h [头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)提供的画线功能。这里 x1、y1 是直线的第一坐标，x2、y2 分别是直线的第二坐标。
*   [**【圆(x，y，r)**](https://www.geeksforgeeks.org/draw-circle-c-graphics/#:~:text=h%20contains%20circle()%20function, the%20Radius%20of%20the%20circle.) **:** 是 graphics.h 头文件提供的画圆的功能。x，y 是圆的中心点，r 是圆的半径。
*   [**矩形(X1，Y1，X2，Y2)**](https://www.geeksforgeeks.org/draw-rectangle-c-graphics/) **:** 用于创建矩形。矩形必须使用左上角和右下角的坐标绘制。左上角的 X 坐标和 Y 坐标分别为 **X1** 和 **Y1** ，右下角的 X 坐标和 Y 坐标分别为 **X2** 和 **Y2** 。
*   **延迟(n):** 用于将节目保持特定的时间段。这里 n 是你想保持程序的秒数。
*   [**【clear device()**](https://www.geeksforgeeks.org/cleardevice-function-c/)**:用于图形模式下的清屏。它将光标的位置设置为其初始位置，即(0，0)坐标。**
*   [**closegraph()**](https://www.geeksforgeeks.org/closegraph-function-c/) **:用于关闭图形。**

**进场:**以下是生成移动周期的步骤:

*   将这三个参数传递给 [**initgraph()函数**](https://www.geeksforgeeks.org/basic-graphic-programming-in-c/) 来初始化图形驱动程序和图形模式。
*   通过画线创建循环的上体。
*   通过绘制圆来创建循环的轮子，并选择坐标，以便轮子正好在循环的上半身下方对齐。
*   下一步是通过画直线来创建道路，通过画矩形来创建石头。
*   选择坐标，使自行车刚好在道路上方。
*   使用循环连续改变自行车的位置，使其看起来像在路上行驶。

下面是上述方法的实现:

## C++

```cpp
// C++ program to draw the moving
// cycle using computer graphics

#include <conio.h>
#include <dos.h>
#include <graphics.h>
#include <iostream.h>

// Driver code
int main()
{
    int gd = DETECT, gm, i, a;

    // Path of the program
    initgraph(&gd, &gm, "C:\\TURBOC3\\BGI");

    // Move the cycle
    for (i = 0; i < 600; i++) {
        // Upper body of cycle
        line(50 + i, 405, 100 + i, 405);
        line(75 + i, 375, 125 + i, 375);
        line(50 + i, 405, 75 + i, 375);
        line(100 + i, 405, 100 + i, 345);
        line(150 + i, 405, 100 + i, 345);
        line(75 + i, 345, 75 + i, 370);
        line(70 + i, 370, 80 + i, 370);
        line(80 + i, 345, 100 + i, 345);

        // Wheel
        circle(150 + i, 405, 30);
        circle(50 + i, 405, 30);

        // Road
        line(0, 436, getmaxx(), 436);

        // Stone
        rectangle(getmaxx() - i, 436,
                  650 - i, 431);

        // Stop the screen for 10 secs
        delay(10);

        // Clear the screen
        cleardevice();
    }

    getch();

    // Close the graph
    closegraph();
}
```

**输出:**

<video class="wp-video-shortcode" id="video-650104-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210722133810/cycle.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210722133810/cycle.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210722133810/cycle.mp4)</video>