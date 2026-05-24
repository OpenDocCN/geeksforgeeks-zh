# 使用图形绘制移动船只的 C 程序

> 原文:[https://www . geesforgeks . org/c-program-to-draw-a-move-boat-use-graphics/](https://www.geeksforgeeks.org/c-program-to-draw-a-moving-boat-using-graphics/)

在 [C 图形](https://www.geeksforgeeks.org/add-graphics-h-c-library-gcc-compiler-linux/)中， [**graphics.h**](https://www.geeksforgeeks.org/include-graphics-h-codeblocks/) 函数用于绘制不同的形状，如圆形、矩形等，以不同的格式(不同的字体和颜色)显示文本(任何消息)。通过使用 header graphics.h 中的功能，还可以制作程序、动画和不同的游戏。在本文中，我们将讨论如何使用[图形](https://www.geeksforgeeks.org/applications-of-computer-graphics/)在 C 中绘制移动的船。

**使用的功能:**

*   [**getmaxx()**](https://www.geeksforgeeks.org/getmaxx-function-c/)**:graphics . h[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)包含 getmaxx()函数，返回当前图形模式和驱动的最大 **X** 坐标。**
*   [**【setcolor(N)**](https://www.geeksforgeeks.org/setcolor-function-c/)**:**头文件 graphics.h 中的 **setcolor()函数**用于将当前绘图颜色更改为新颜色。
*   [**setlinestyle(linestyle，upattern，thickness):**](https://www.geeksforgeeks.org/setlinestyle-function-c/) 头文件 graphics.h 中的 setlinestyle()函数为所有使用 line、lineto、矩形、drawpoly 等函数绘制的线条设置样式。
*   [**矩形(X1，Y1，X2，Y2)**](https://www.geeksforgeeks.org/draw-rectangle-c-graphics/) **:** 用于创建矩形。矩形必须使用左上角和右下角的坐标绘制。左上角的 X 坐标和 Y 坐标分别为 **X1** 和 **Y1** ，右下角的 X 坐标和 Y 坐标分别为 **X2** 和 **Y2** 。
*   [**【漫填(图案、颜色)**](https://www.geeksforgeeks.org/setfillstyle-floodfill-c/) **:** 该功能用于填充密闭空间。为了填充该区域，使用当前的填充图案和颜色。

**进场:**按照以下步骤生成移动船:

*   将三个参数传递给 [**initgraph()函数**](https://www.geeksforgeeks.org/add-graphics-h-c-library-gcc-compiler-linux/) 来初始化[图形驱动程序](https://www.geeksforgeeks.org/basic-graphic-programming-in-c/)和图形模式。
*   通过考虑两个变量 **X** 和 **Y** 来初始化船的位置。
*   通过[绘制一个矩形](https://www.geeksforgeeks.org/draw-rectangle-c-graphics/)创建一条船将在其上移动的河流/海洋，并用浅蓝色油漆填充它，使其看起来像一条河流/海洋。
*   选择坐标，使船刚好在河/海的上方。
*   使用[循环](https://www.geeksforgeeks.org/range-based-loop-c/)连续改变船的位置，使它看起来像是在河里移动。

下面是上述方法的实现:

## C

```cpp
// C program to draw the moving boat
// using c graphics

#include <conio.h>
#include <dos.h>
#include <graphics.h>
#include <stdio.h>

// Driver Code
int main()
{
    // Initialize graphic driver
    int gdriver = DETECT, gmode, err;
    int i = 0, j, x, y, x1, y1, x2, y2;

    // Start graphics mode by passing
    // three arguments to initgraph()

    // &gdriver is the address of the
    // gdriver variable.

    // &gmode is the address of gmode

    // "C:Turboc3BGI" is the directory
    // path where BGI files are stored
    initgraph(&gdriver, &gmode,
              "C:\\Turboc3\\BGI");
    err = graphresult();

    if (err != grOk) {
        printf("Graphics Error: %s\n",
               grapherrormsg(err));

        return 0;
    }

    j = 0;

    // Initialize position for boat
    x = 50, y = getmaxy() / 2 + 140;

    while (x + 60 < getmaxx()
           && (!kbhit())) {

        // Set the positions for rain
        x1 = 10, i = y1 = 0;
        x2 = 0, y2 = 50;

        // Clears graphic screen
        cleardevice();

        // Set the color of river/sea
        setcolor(LIGHTBLUE);
        setlinestyle(SOLID_LINE, 1, 1);
        setfillstyle(SOLID_FILL,
                     LIGHTBLUE);

        // Draw the river/sea
        rectangle(0, getmaxy() / 2 + 150,
                  getmaxx(), getmaxy());
        floodfill(getmaxx() - 10,
                  getmaxy() - 10,
                  LIGHTBLUE);

        // Rain drops
        setlinestyle(DASHED_LINE, 1, 2);

        while (i < 700) {
            line(x1, y1, x2, y2);
            x1 = x1 + 20;
            y2 = y2 + 50;
            i++ ;
        }

        // Drawing the boat
        setlinestyle(SOLID_LINE, 1, 2);
        setcolor(BROWN);

        setfillstyle(SOLID_FILL, BROWN);
        sector(x, y, 180, 360, 50, 10);

        setcolor(DARKGRAY);
        setlinestyle(SOLID_LINE, 1, 3);

        // Leg and body of stick man
        line(x + 40, y - 15, x + 40, y - 40);
        line(x + 40, y - 15, x + 45, y - 10);
        line(x + 45, y - 10, x + 45, y);
        line(x + 40, y - 15, x + 37, y);

        // Head and hand of stick man
        circle(x + 40, y - 45, 5);
        line(x + 40, y - 35, x + 50, y - 30);
        line(x + 40, y - 35, x + 35, y - 32);
        line(x + 35, y - 32, x + 45, y - 25);
        line(x + 60, y - 45, x + 27, y + 10);

        // Moving the position of
        // boat and stick man
        x++ ;

        setcolor(LIGHTBLUE);
        delay(250);

        // Clears the graphic device
        cleardevice();

        // Drawing sea/river
        setlinestyle(SOLID_LINE, 1, 1);
        setfillstyle(SOLID_FILL,
                     LIGHTBLUE);

        rectangle(0, getmaxy() / 2 + 150,
                  getmaxx(), getmaxy());
        floodfill(getmaxx() - 10,
                  getmaxy() - 10,
                  LIGHTBLUE);

        // Rain drops
        setlinestyle(DASHED_LINE, 1, 2);
        x1 = 10, i = y1 = 0;
        x2 = 0, y2 = 70;

        while (i < 700) {
            line(x1, y1, x2, y2);
            x1 = x1 + 30;
            y2 = y2 + 60;
            i++ ;
        }

        // Drawing the boat
        setlinestyle(SOLID_LINE, 1, 1);
        setcolor(BROWN);
        setfillstyle(SOLID_FILL, BROWN);
        sector(x, y, 180, 360, 50, 10);

        // Body and leg of stic man
        setcolor(DARKGRAY);
        setlinestyle(SOLID_LINE, 1, 3);
        line(x + 40, y - 15, x + 40, y - 40);
        line(x + 40, y - 15, x + 45, y - 10);
        line(x + 45, y - 10, x + 45, y);
        line(x + 40, y - 15, x + 37, y);

        // Head hands of stick man
        circle(x + 40, y - 45, 5);
        line(x + 40, y - 35, x + 52, y - 30);
        line(x + 40, y - 35, x + 37, y - 32);
        line(x + 37, y - 32, x + 49, y - 25);
        line(x + 60, y - 45, x + 27, y + 10);

        // Forwarding the position of
        // the boat
        x++ ;

        // Sleep for 250 milliseconds
        delay(250);

        // Clears the graphic device
        cleardevice();
        j++ ;
    }

    getch();

    // Deallocate memory allocated
    // for graphic screen
    closegraph();

    return 0;
}
```

**输出:**

<video class="wp-video-shortcode" id="video-604743-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210511212940/New-video.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210511212940/New-video.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210511212940/New-video.mp4)</video>