# 在 C/C++ 中使用计算机图形学制作河内塔的动画

> 原文:[https://www . geeksforgeeks . org/animation-of-of-tower-of-of-of-of-Hanoi-in-computer-graphics-in-c-CPP/](https://www.geeksforgeeks.org/animation-of-tower-of-hanoi-using-computer-graphics-in-c-cpp/)

任务是使用 [C](https://www.geeksforgeeks.org/c-programming-language/) / [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的[计算机图形](https://www.geeksforgeeks.org/introduction-to-computer-graphics/)设计河内[塔。](https://www.geeksforgeeks.org/iterative-tower-of-hanoi/)

[**河内塔**](https://www.geeksforgeeks.org/c-program-for-tower-of-hanoi/) **:** 这是一个数学问题，有三座塔和 **N** 个圆盘。问题是按照以下规则将所有磁盘从第一个塔移动到第三个塔:

*   一次只能移动一个磁盘，并且一次不能移动两个或两个以上的磁盘。
*   移动磁盘时，用户必须记住，较小的磁盘总是在较大的磁盘之上。
*   这意味着大的在塔的底部，小的在塔顶。

**使用的功能:**

*   **矩形(l，t，r，b):** 来自 [graphics.h](https://www.geeksforgeeks.org/computer-graphics-2/) 头文件的函数，该文件从左(l)到右(r) &从上(t)到下(b)绘制一个矩形。
*   **线(a1，b1，a2，B2):**graphics . h 头文件中的一个函数，它从点 **(a1，b1)** 到点 **(a2，b2)** 绘制一条线。
*   **setfillstyle(模式，颜色):**来自 graphics.h [头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)的一个函数，通过它我们可以给出一个绘图的模式&也是一个特定的颜色。
*   **泛洪填充(A，b，c):**graphics . h 头文件中的一个函数，通过它我们可以在以(A，b)为中心的特定有界区域中进行着色& c 为边框颜色。
*   **outextxy(int x，int y，char * string):**graphics . h 头文件中的一个函数，通过它我们可以打印任何语句，其中，x，y 是点的坐标，第三个参数包含要显示的字符串的地址。
*   **settextstyle(int font，int direction，int font _ size):**graphics . h 头文件中的一个函数，通过它我们可以制作可打印文本的样式，其中 font 参数指定文本的字体，direction 可以是 **HORIZ_DIR(从左到右)**或 **VERT_DIR(从下到上)**。

**进场:**

*   这里制作了一个动画，其中实现了 3 盘河内塔问题。整个过程将分 7 个阶段完成。
*   总共定义了九个函数，start()、p1()、p2()、p3()、p4()、p5()、p6()、p7()、outline()。
*   首先，调用 start()函数。打印一条消息“开始状态”。然后使用 rectangle()函数实现总共三个磁盘。然后涂上颜色。下面的大的是红色的，中间的是蓝色的&上面的小的是绿色的。所有着色都是通过 **setfillstyle()** 和 **floodfill()** 功能完成的。最后呼叫大纲()。
*   在 outline()函数中，使用 **line()函数**实现塔，并打印塔的数量。
*   然后调用 p1()函数。cleardevice()函数将清除屏幕。在这里，移动较小的绿色磁盘到第三个塔。然后调用 outline()函数。另外，打印信息**“第一阶段”**。
*   然后调用 p2()函数。cleardevice()函数将清除屏幕。在这里，移动较小的蓝色磁盘到第二个塔。然后还会调用 outline()函数。另外，打印信息**“第二阶段”**。
*   然后会调用 p3()函数。cleardevice()函数将清除屏幕。在这里，将较小的绿色磁盘移动到蓝色磁盘顶部的第二个塔中。然后还会调用 outline()函数。另外，打印信息**“第三阶段”**。
*   然后会调用 p4()函数。cleardevice()函数将清除屏幕。这里，把更大的红盘移到第三个塔。然后还会调用 outline()函数。另外，打印信息**“第四阶段”**。
*   然后会调用 p5()函数。cleardevice()函数将清除屏幕。在这里，移动较小的绿色磁盘到第一个塔。然后也调用 outline()函数。另外，打印信息**“第五阶段”**。
*   然后调用 p6()函数。cleardevice()函数将清除屏幕。在这里，将较小的蓝色圆盘移动到红色圆盘顶部的第三个塔上。然后还会调用 outline()函数。另外，打印信息**“第六阶段”**。
*   然后会调用 p7()函数。cleardevice()函数将清除屏幕。在这里，将较小的绿色磁盘移动到蓝色磁盘顶部的第三个塔中。然后还会调用 outline()函数。另外，打印信息**“第七阶段”**。因此动画就完成了。**T3】**

下面是上述方法的实现:

## C

```cpp
// C program for the above approach
#include <conio.h>
#include <graphics.h>
#include <stdio.h>

// Function for moving the Green Disk
// to Third Tower On Top Of Blue Disk
void p7()
{
    getch();
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "7th Phase");
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(850, 500, 950, 550);
    floodfill(855, 545, 15);
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(875, 450, 925, 500);
    floodfill(880, 495, 15);
    setfillstyle(SOLID_FILL, RED);
    rectangle(825, 600, 975, 550);
    floodfill(830, 555, 15);

    // Calling outline() function
    outline();
}

// Function to find the moving the Blue
// Disk To Third Tower On Top Of Red Disk
void p6()
{
    getch();
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "6th Phase");
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(850, 500, 950, 550);
    floodfill(855, 545, 15);
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(275, 600, 325, 550);
    floodfill(280, 595, 15);
    setfillstyle(SOLID_FILL, RED);
    rectangle(825, 600, 975, 550);
    floodfill(830, 555, 15);

    // Calling outline() function
    outline();
}

// Function to find the moving Green Disk
// To the First Tower
void p5()
{
    getch();
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "5th Phase");
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(550, 550, 650, 600);
    floodfill(555, 595, 15);
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(275, 600, 325, 550);
    floodfill(280, 595, 15);
    setfillstyle(SOLID_FILL, RED);
    rectangle(825, 600, 975, 550);
    floodfill(830, 555, 15);

    // Calling outline() function
    outline();
}

// Moving Red Disk To Third Tower
void p4()
{
    getch();
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "4th Phase");
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(550, 550, 650, 600);
    floodfill(555, 595, 15);
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(575, 500, 625, 550);
    floodfill(580, 545, 15);
    setfillstyle(SOLID_FILL, RED);
    rectangle(825, 600, 975, 550);
    floodfill(830, 555, 15);

    // Calling outline() function
    outline();
}

// Function for moving the Green Disk
// To Second Tower On Top Of Blue Disk
void p3()
{
    getch();
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "3rd Phase");
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(550, 550, 650, 600);
    floodfill(555, 595, 15);
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(575, 500, 625, 550);
    floodfill(580, 545, 15);
    setfillstyle(SOLID_FILL, RED);
    rectangle(225, 550, 375, 600);
    floodfill(230, 590, 15);

    // Calling outline() function
    outline();
}

// Function for moving the Blue Disk
// To Second Tower
void p2()
{
    getch();
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "2nd Phase");
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(550, 550, 650, 600);
    floodfill(555, 595, 15);
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(875, 600, 925, 550);
    floodfill(880, 595, 15);
    setfillstyle(SOLID_FILL, RED);
    rectangle(225, 550, 375, 600);
    floodfill(230, 590, 15);

    // Calling outline() function
    outline();
}

// Function for moving the Green Disk
// To Third Tower
void p1()
{
    getch();
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "1st Phase");
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(875, 600, 925, 550);
    floodfill(880, 595, 15);
    setfillstyle(SOLID_FILL, RED);
    rectangle(225, 550, 375, 600);
    floodfill(230, 590, 15);
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(250, 500, 350, 550);
    floodfill(255, 545, 15);

    // Calling outline() function
    outline();
}

// Function to start the animations
void start()
{
    // Starting Condition
    cleardevice();
    settextstyle(8, 0, 4);
    outtextxy(500, 50, "Begining State");

    // Red Coloring Of Disk
    setfillstyle(SOLID_FILL, RED);
    rectangle(225, 550, 375, 600);
    floodfill(230, 590, 15);

    // Blue Coloring Of Disk
    setfillstyle(SOLID_FILL, BLUE);
    rectangle(250, 500, 350, 550);
    floodfill(255, 545, 15);

    // Green Coloring Of Disk
    setfillstyle(SOLID_FILL, GREEN);
    rectangle(275, 450, 325, 500);
    floodfill(285, 495, 15);

    // calling outline() function
    outline();
}

// Function to print the outlines of
// the animations
void outline()
{
    // Main Base
    line(100, 600, 1100, 600);

    // 1st Line
    line(300, 600, 300, 300);

    // 2nd Line
    line(600, 600, 600, 300);

    // 3rd Line
    line(900, 600, 900, 300);

    // Printing Message
    settextstyle(8, 0, 2);
    outtextxy(290, 620, "(1)");
    outtextxy(590, 620, "(2)");
    outtextxy(890, 620, "(3)");
}
// Driver Code
void main()
{
    int gd = DETECT, gm;

    // Initialize of gdriver with
    // DETECT macros
    initgraph(&gd, &gm, "C:\\turboc3\\bgi");

    // Calling start() function
    start();

    // Calling p1() function
    p1();

    // Calling p2() function
    p2();

    // Calling p3() function
    p3();

    // Calling p4() function
    p4();

    // Calling p5() function
    p5();

    // Calling p6() function
    p6();

    // Calling p7() function
    p7();

    // Holding screen for a while
    getch();

    // Close the initialized gdriver
    closegraph();
}
```

**输出:**

<video class="wp-video-shortcode" id="video-653172-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210714150352/TOWER-OF-HANOI.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210714150352/TOWER-OF-HANOI.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210714150352/TOWER-OF-HANOI.mp4)</video>