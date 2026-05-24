# 使用图形的声音骰子模拟器

> 原文:[https://www . geesforgeks . org/dice-带有声音的模拟器-使用图形/](https://www.geeksforgeeks.org/dice-simulator-with-sound-using-graphics/)

[**【图形】**](https://www.geeksforgeeks.org/introduction-to-computer-graphics/geeksforgeeks.org/computer-graphics-2/) 被定义为任何一幅草图或一幅图画或一个特殊的网络，以图像的方式表示一些有意义的信息。[计算机图形学](https://www.geeksforgeeks.org/introduction-to-computer-graphics/)用于需要处理一组图像或以像素形式创建图像并在计算机上绘制的地方。它可以用于数字摄影、电影、娱乐、电子产品以及所有其他所需的核心技术。

在本文中，我们将讨论使用计算机图形模拟从 **1** 到 **6** 的骰子数值。为了实现这个模拟，使用 [graphics.h](https://www.geeksforgeeks.org/computer-graphics-2/) [头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)制作骰子，使用 [**dos.h**](https://www.geeksforgeeks.org/dos-h-header-in-c-with-examples/) 在掷出骰子时发出哔哔声，使用 [stdlib.h](https://www.geeksforgeeks.org/whats-difference-between-and/) 头文件进行 [**随机()函数**](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/) 生成从 **1** 到 **6** 的随机数。

**进场:**

*   使用[功能](https://www.geeksforgeeks.org/functions-in-c/) **初始化图形路径()**。
*   [循环](https://www.geeksforgeeks.org/range-based-loop-c/)直到程序结束，执行以下步骤:
    *   从用户处获取字符输入，并:
        *   如果字符是**空格**，则从范围**【1，6】**中生成任意随机数，并使用矩形函数在正方形中显示该数字。
        *   如果角色是 **0** ，那么[跳出循环](https://www.geeksforgeeks.org/break-statement-cc/)。
        *   如果字符不是 **O** 或**空格**则显示消息只按字符 **0** 和**空格**。
*   模拟器结束后，使用[**【closegraph()**](https://www.geeksforgeeks.org/closegraph-function-c/)功能关闭图形。

下面是 [C 程序](https://www.geeksforgeeks.org/c-programming-language/)用图形说明骰子模拟器:

## C

```cpp
// C program to illustrate the dice
// simulator using graphics

#include <conio.h>
#include <graphics.h>
#include <stdio.h>
#include <stdlib.h>

// Driver Code
void main()
{
    int gd = DETECT, gm, i;
    int font = 7, direction = 0;
    int font_size = 4, r;
    char press, key, num[1];
    char value[6] = "624531";

    // Initialize the graphics path
    initgraph(&gd, &gm, "C:\\TC\\BGI");

    // Heading
    setcolor(WHITE);
    settextstyle(font, direction,
                 font_size);

    outtextxy(100, 10,
              "-----DICE SIMULATOR-----");

    setcolor(2);
    settextstyle(10, 0, 1);
    outtextxy(120, 180,
              "\"enter (space) to"
              " throw dice\"");
    press = ' ';

    // Iterate until ask to throw
    // the dice
    while (1) {
        key = getch();
        if (press == key) {

            // Beep sound after
            // throwing dice
            sound(3000);
            delay(10);
            nosound();
            cleardevice();
            for (i = 0; i < 40; i++) {
                delay(5);

                // Rectangle
                rectangle(270 + i, 190 + i,
                          350 - i, 270 - i);
            }

            setcolor(WHITE);
            settextstyle(font, direction,
                         font_size);
            outtextxy(100, 10,
                      "-----DICE SIMULATOR-----");

            setcolor(10);
            settextstyle(10, 0, 1);

            // Print the message to
            // display the game
            outtextxy(5, 60,
                      "\"press 0 (zero) "
                      "for exit.\"");
            outtextxy(
                5, 100,
                "\"enter (space) to "
                "throw dice again.\"\n");

            for (i = 1; i < 40; i++) {
                delay(5);
                setcolor(1);

                // Rectangle
                rectangle(310 - i, 230 - i,
                          310 + i, 230 + i);
            }

            // Generate a random number
            // between 1 to 6
            r = random(6);
            num[1] = value[r];

            setcolor(6);

            // Update the style of text
            settextstyle(1, 0, 6);

            // Print the number
            outtextxy(300, 200, num);
        }
        else if (key == '0') {
            break;
        }
        else {

            // Clear the device
            cleardevice();

            // Update background color
            setcolor(WHITE);
            settextstyle(font, direction,
                         font_size);

            // Print the message
            outtextxy(100, 10,
                      "-----DICE SIM"
                      "ULATOR-----");

            setcolor(4);
            settextstyle(10, 0, 1);

            // For wrong key pressed
            outtextxy(170, 110,
                      "\"you enter wrong key\"");
            setcolor(14);

            // Exiting the code
            outtextxy(170, 170,
                      "\"Enter 0 (zero)"
                      " for exit\"");
            setcolor(9);
            outtextxy(300, 220, "(or)");
            setcolor(5);

            // For starting the dice
            // roll again
            outtextxy(
                90, 270,
                "\"Enter (space) to"
                " throw dice again\"");
        }
    }
    closegraph();
}
```

**输出**T2】

<video class="wp-video-shortcode" id="video-618139-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210531201057/Dice-simulator-in-c-using-graphics.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210531201057/Dice-simulator-in-c-using-graphics.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210531201057/Dice-simulator-in-c-using-graphics.mp4)</video>