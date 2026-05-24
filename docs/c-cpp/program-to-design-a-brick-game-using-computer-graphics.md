# 使用计算机图形设计砖块游戏的程序

> 原文:[https://www . geeksforgeeks . org/程序到设计-使用计算机图形的砖块游戏/](https://www.geeksforgeeks.org/program-to-design-a-brick-game-using-computer-graphics/)

在 [C 图形](https://www.geeksforgeeks.org/creating-rainbow-using-graphics-programming-c/)中， [graphics.h](https://www.geeksforgeeks.org/include-graphics-h-codeblocks/) 功能用于绘制圆形、矩形等不同形状，以不同格式(不同字体和颜色)显示文本(任何消息)。通过使用 graphics.h 程序，可以设计动画和游戏。这些对初学者很有用。

**使用的功能:**

*   [**【矩形(l，t，r，b)**](https://www.geeksforgeeks.org/draw-rectangle-c-graphics/)**:**graphics . h 头文件中的一个函数，从左(l)到右(r)，从上(t)到下(b)绘制一个矩形。
*   [**线(a1，b1，a2，b2)**](https://www.geeksforgeeks.org/draw-line-c-graphics/)**:**graphics . h 头文件中的一个函数，从(a1，b1)点到(a2，B2)点绘制一条线。
*   [**【setfillstyle(图案，颜色)**](https://www.geeksforgeeks.org/setfillstyle-floodfill-c/)**:**graphics . h 头文件中的一个函数，通过它可以给出一个绘图的图案和一种特定的颜色。
*   [**【漫填(A，b，c):**](https://www.geeksforgeeks.org/setfillstyle-floodfill-c/)graphics . h 头文件中的一个函数，通过它可以给以(A，b)为中心、c 为边框颜色的特定有界区域着色。
*   [**【outextxy(int x，int y，char * string)**](https://www.geeksforgeeks.org/outtextxy-function-c/)**:**graphics . h 头文件中的一个函数，通过它可以打印任何语句，其中，x，y 是点的坐标，第三个参数包含要显示的字符串的地址。
*   [**【settextstyle(int font，int direction，int font _ size)**](https://www.geeksforgeeks.org/settextstyle-function-c/)**:**graphics . h 头文件中的一个函数，可用于可打印文本的样式，其中 font 参数指定了文本的字体。方向可以是水平方向(从左到右)或垂直方向(从下到上)。

**进场:**

*   这是一个砖块游戏，砖块是随机颜色的。
*   有 3 个列可以放置砖块。
*   如果两块相同颜色的砖相邻，它们都会消失，分数会增加 10 分。
*   如果砖块碰到了游戏区的顶部，那么游戏就结束了。下面是一段视频来解释这个游戏是如何工作的。

下面是实现相同的程序:

## C

```cpp
// C program for the above approach
#include <conio.h>
#include <dos.h>
#include <graphics.h>
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void outline()
{
    int u = 400;

    // Storing Box Outline
    rectangle(700, 300, 1000, 900);

    // Vertical Lines To Make
    // Divisions
    line(800, 300, 800, 900);
    line(900, 300, 900, 900);

    // Making Horizontal Line Using
    // While Function
    while (u <= 900) {
        line(700, u, 1000, u);
        u = u + 100;
    }

    // Printing The Instruction
    // On Screen
    settextstyle(10, 0, 3);
    outtextxy(20, 100, "FOR MOVE LEFT PRESS 'l'");
    outtextxy(20, 200, "FOR MOVE RIGHT PRESS 'r'");
    outtextxy(20, 300, "FOR MOVE MIDDLE PRESS 'm'");
}

// Driver Code
void main()
{
    int gd = DETECT, gm;

    // Initialize of gdriver with
    // DETECT macros
    initgraph(&gd, &gm, "C:\\turboc3\\bgi");

    // Declaring & Initialising Variables
    int a = 800, b = 50, c = 900, d = 150,
        x, left[10], right[10], mid[10],
        up = 5, low = 2, lb = 900, mb = 900,
        rb = 900, i = 0, j = 0, k = 0,
        score = 0, p;
    char z, str[3];

    // Calling outline() function
    outline();

    // Creating Infinite Loop To Make
    // Continuous Use OF Game
    while (1) {
        // Creating & Naming The
        // Brick Box
        settextstyle(8, 0, 2);
        outtextxy(800, 10, "Brick Box");
        rectangle(a, b, c, d);

        // Generating Random Color Number
        x = (rand() % (up - low + 1)) + low;
        setfillstyle(SOLID_FILL, x);
        floodfill(a + 5, d - 5, 15);

        // Getting Input To Move Bricks
        z = getch();

        // Operations For Place The Bricks
        // In Left Side
        if (z == 'l') {
            // Creating & Naming The Left
            // Sub-Box
            settextstyle(8, 0, 2);
            outtextxy(630, 10, "Left Sub-Box");

            rectangle(a - 150, b, c - 150, d);
            floodfill(a - 55, d - 5, 15);
            delay(200);
            setfillstyle(SOLID_FILL, BLACK);
            floodfill(a - 55, d - 5, 15);
            rectangle(a - 100, lb - 100,
                      c - 100, lb);
            setfillstyle(SOLID_FILL, x);
            floodfill(a - 5, lb - 5, 15);
            delay(200);

            // Decreasing The Base Of
            // Left Side
            lb = lb - 100;

            // Storing Corresponding Color
            // In Left[] Array
            left[i] = x;
            i++ ;

            // Process To Check Is There Any
            // Matching In The Left Side By
            // Upside Down
            if (left[0] == left[1]) {
                lb = 900;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a - 5, lb - 5, 15);
                floodfill(a - 5, lb - 105, 15);
                score = score + 10;
                i = 0;
                left[1] = 0;
            }
            else if (left[1] == left[2]) {
                lb = 800;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a - 5, lb - 5, 15);
                floodfill(a - 5, lb - 105, 15);
                score = score + 10;
                i = 1;
                left[2] = 0;
            }
            else if (left[2] == left[3]) {
                lb = 700;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a - 5, lb - 5, 15);
                floodfill(a - 5, lb - 105, 15);
                score = score + 10;
                i = 2;
                left[3] = 0;
            }
            else if (left[3] == left[4]) {
                lb = 600;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a - 5, lb - 5, 15);
                floodfill(a - 5, lb - 105, 15);
                score = score + 10;
                i = 3;
                left[4] = 0;
            }
            else if (left[4] == left[5]) {
                lb = 500;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a - 5, lb - 5, 15);
                floodfill(a - 5, lb - 105, 15);
                score = score + 10;
                i = 4;
                left[5] = 0;
            }
            else
                p = 0;

            // Loop Breaking Condition For
            // Left Side
            if (lb < 400)
                break;
        }

        // Operations For Place The Bricks
        // In Right Side
        else if (z == 'r') {
            // Creating & Naming The Left
            // Sub-Box
            settextstyle(8, 0, 2);
            outtextxy(970, 10, "Right Sub-Box");

            rectangle(a + 150, b, c + 150, d);
            floodfill(a + 155, d - 5, 15);
            delay(200);
            setfillstyle(SOLID_FILL, BLACK);
            floodfill(a + 155, d - 5, 15);
            rectangle(a + 100, rb - 100,
                      c + 100, rb);
            setfillstyle(SOLID_FILL, x);
            floodfill(a + 105, rb - 5, 15);
            delay(200);

            // Decreasing The Base Of
            // Right Side
            rb = rb - 100;

            // Storing Corresponding Color
            // In Right[] Array
            right[j] = x;
            j++ ;

            // Process to Check Is There Any Matching
            // In The Right Side By Upside Down
            if (right[0] == right[1]) {
                rb = 900;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 105, rb - 5, 15);
                floodfill(a + 105, rb - 105, 15);
                score = score + 10;
                j = 0;
                right[1] = 0;
            }
            else if (right[1] == right[2]) {
                rb = 800;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 105, rb - 5, 15);
                floodfill(a + 105, rb - 105, 15);
                score = score + 10;
                j = 1;
                right[2] = 0;
            }
            else if (right[2] == right[3]) {
                rb = 700;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 105, rb - 5, 15);
                floodfill(a + 105, rb - 105, 15);
                score = score + 10;
                j = 2;
                right[3] = 0;
            }
            else if (right[3] == right[4]) {
                rb = 600;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 105, rb - 5, 15);
                floodfill(a + 105, rb - 105, 15);
                score = score + 10;
                j = 3;
                right[4] = 0;
            }
            else if (right[4] == right[5]) {
                rb = 500;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 105, rb - 5, 15);
                floodfill(a + 105, rb - 105, 15);
                score = score + 10;
                j = 4;
                right[5] = 0;
            }
            else
                p = 0;

            // Loop Breaking Condition For
            // Right Side
            if (rb - 100 < 300)
                break;
        }

        // Operations For Place The Bricks
        // In Middle Side
        else {
            rectangle(a, mb - 100, c, mb);
            floodfill(a + 5, mb - 5, 15);
            delay(200);

            // Decreasing The Base Of
            // Middle Side
            mb = mb - 100;

            // Storing Corresponding Color In
            // Mid[] Array
            mid[k] = x;
            k++ ;

            // Process To Check Is There Any
            // Matching In The Middle Side
            // By Upside Down
            if (mid[0] == mid[1]) {
                mb = 900;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 5, mb - 5, 15);
                floodfill(a + 5, mb - 105, 15);
                score = score + 10;
                k = 0;
                mid[1] = 0;
            }
            else if (mid[1] == mid[2]) {
                mb = 800;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 5, mb - 5, 15);
                floodfill(a + 5, mb - 105, 15);
                score = score + 10;
                k = 1;
                mid[2] = 0;
            }
            else if (mid[2] == mid[3]) {
                mb = 700;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 5, mb - 5, 15);
                floodfill(a + 5, mb - 105, 15);
                score = score + 10;
                k = 2;
                mid[3] = 0;
            }
            else if (mid[3] == mid[4]) {
                mb = 600;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 5, mb - 5, 15);
                floodfill(a + 5, mb - 105, 15);
                score = score + 10;
                k = 3;
                mid[4] = 0;
            }
            else if (mid[4] == mid[5]) {
                mb = 500;
                setfillstyle(SOLID_FILL, BLACK);
                floodfill(a + 5, mb - 5, 15);
                floodfill(a + 5, mb - 105, 15);
                score = score + 10;
                k = 4;
                mid[5] = 0;
            }
            else
                p = 0;

            // Loop Breaking Condition For
            // Middle Side
            if (mb - 100 < 300)
                break;
        }

        // Time Delay
        delay(200);

        // Display Score Whenever There Is
        // Any Match
        sprintf(str, "%d", score);
        outtextxy(100, 600, "SCORE: ");
        outtextxy(100, 700, str);
    }

    // Time Delay
    delay(500);

    // Clearing The Screen When Game
    // Is Over
    cleardevice();

    // Holding screen for a while
    getch();

    // Close the initialized gdriver
    closegraph();
}
```

**输出:**

<video class="wp-video-shortcode" id="video-619596-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210606164508/BRICK-GAME-OUTPUT.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210606164508/BRICK-GAME-OUTPUT.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210606164508/BRICK-GAME-OUTPUT.mp4)</video>