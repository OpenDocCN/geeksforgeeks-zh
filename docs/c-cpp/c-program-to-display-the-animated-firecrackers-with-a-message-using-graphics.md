# 使用图形显示带有信息的动画鞭炮的程序

> 原文:[https://www . geesforgeks . org/c-程序-用图形显示带有消息的动画鞭炮/](https://www.geeksforgeeks.org/c-program-to-display-the-animated-firecrackers-with-a-message-using-graphics/)

在本文中，我们将讨论如何使用[图形](https://www.geeksforgeeks.org/basic-graphic-programming-in-c/)绘制**火箭**。

方法:

*   在[主()](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/)功能中，调用**发射()**功能。launch()函数是一个基础，它将反复调用 **fire() & mess()** 函数，直到满足给定条件。
*   **mess()** 功能将包含生日消息。
    *   要描绘生日消息，请使用[setextstyle()](https://www.geeksforgeeks.org/settextstyle-function-c/)&[outextxy()](https://www.geeksforgeeks.org/outtextxy-function-c/)功能。根据用户的输入，这些条件决定了烟花可以达到的最大高度。
    *   请注意，任何文本都可以在函数调用之前编写。
*   fire()函数最初调用 cracker()函数。
    *   鞭炮()功能利用图形中的[线()功能，借助三角形实现五个鞭炮。](https://www.geeksforgeeks.org/draw-line-c-graphics/)
    *   要给[着色，可以使用 setfillstyle()&flood fill()](https://www.geeksforgeeks.org/setfillstyle-floodfill-c/)功能。
    *   fire()函数将使用 **line()** 函数实现多条相同长度的线。
*   [头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)[【time . h】](https://www.geeksforgeeks.org/time-h-header-file-in-c-with-examples/)用于其中存在的延迟功能。延迟功能将允许我们为动画添加变化。

下面是上述方法的实现:

## C

```cpp
// C program for the above approach

#include <conio.h>
#include <graphics.h>
#include <stdio.h>
#include <time.h>

// Function to display the crackers
void crackers()
{
    // 1st Cracker
    setfillstyle(SOLID_FILL, RED);
    line(80, 680, 130, 680);
    line(80, 680, 105, 630);
    line(105, 630, 130, 680);
    floodfill(105, 650, 15);

    // 2nd Cracker
    setfillstyle(SOLID_FILL, BLUE);
    line(300, 680, 350, 680);
    line(300, 680, 325, 630);
    line(325, 630, 350, 680);
    floodfill(325, 650, 15);

    // 3rd Cracker
    setfillstyle(SOLID_FILL, BROWN);
    line(500, 680, 550, 680);
    line(500, 680, 525, 630);
    line(525, 630, 550, 680);
    floodfill(525, 650, 15);

    // 4th Cracker
    setfillstyle(SOLID_FILL, GREEN);
    line(700, 680, 750, 680);
    line(700, 680, 725, 630);
    line(725, 630, 750, 680);
    floodfill(725, 650, 15);

    // 5th Cracker
    setfillstyle(SOLID_FILL, CYAN);
    line(920, 680, 970, 680);
    line(920, 680, 945, 630);
    line(945, 630, 970, 680);
    floodfill(945, 650, 15);
}

// Function to display the crackers
// using the crackers() function
void fire()
{
    int v = 625, u = 630, g = 630, h = 625,
        a = 325, n = 325, e = 325, x = 320, j = 330;
    int b = 525, m = 525, f = 525, y = 520,
        k = 530, c = 725, i = 725, o = 725,
        z = 720, l = 730;
    int t = 630, s = 625;

    // Call the crackers functions
    crackers();

    // Iterate until h is 435
    while (h != 435) {
        crackers();

        // Crackers function
        // called
        line(n, g, n, h);
        line(m, u, m, v);
        line(o, u, o, v);
        line(a, u, x, v);
        line(b, u, y, v);
        line(c, u, z, v);
        line(e, t, j, s);
        line(f, t, k, s);
        line(i, t, l, s);

        // Update the value of
        // variables
        a = a - 10;
        x = x - 10;
        u = u - 10;
        v = v - 10;
        g = g - 10;
        h = h - 10;
        b = b - 10;
        y = y - 10;
        c = c - 10;
        z = z - 10;
        t = t - 10;
        s = s - 10;
        e = e + 10;
        f = f + 10;
        i = i + 10;
        j = j + 10;
        k = k + 10;
        l = l + 10;

        // Delay of 30 ms
        delay(30);
    }
}

// Function to display the birthday
// message
void mess()
{
    // Set the text color
    settextstyle(8, 0, 5);

    // Print the birthday message
    outtextxy(200, 350, "HAPPY"
                        " BIRTHDAY TO "
                        "ANYONE....");
}

// Function to call the fire and the
// mess function repeatedly to make
// the fire crackers
void launch()
{
    int q1 = 630, q2 = 590;

    // While Q2 is not the same
    // as 330
    while (q2 != 330) {
        // Clear the screen
        cleardevice();

        // Call the fire and mess
        // function
        fire();
        mess();

        // Print the lines
        line(105, q1, 105, q2);
        line(945, q1, 945, q2);

        // Update the value of q1
        // and q2
        q1 = q1 - 20;
        q2 = q2 - 20;

        // Call the fire and mess
        // function again
        fire();
        mess();

        // Delay of 30 ms
        delay(30);
    }
}

// Driver Code
void main()
{
    int gd = DETECT, gm;

    // Initialize of gdriver
    initgraph(&gd, &gm, "C:\\"
                        "turboc3\\bgi");

    // Launch the fire
    launch();

    // Fill the left circles and text
    // to white color
    setfillstyle(SOLID_FILL, WHITE);
    circle(105, 370, 20);
    floodfill(104, 371, 15);
    floodfill(106, 371, 15);

    // Fill the right circles and text
    // to white color
    setfillstyle(SOLID_FILL, WHITE);
    circle(945, 370, 20);
    floodfill(944, 371, 15);
    floodfill(946, 371, 15);

    // Hold the screen for a while
    getch();

    // Close the initialized gdriver
    closegraph();

    return 0;
}
```

**输出:**

<video class="wp-video-shortcode" id="video-583353-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210409200019/new.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210409200019/new.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210409200019/new.mp4)</video>