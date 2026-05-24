# C/c++ 中鼠标编程用例|集合 2

> 原文:[https://www . geeksforgeeks . org/c-c-set-2 中的鼠标编程用例/](https://www.geeksforgeeks.org/use-cases-of-mouse-programming-in-c-c-set-2/)

在本文中，我们将讨论[鼠标编程](https://www.geeksforgeeks.org/mouse-programming-in-c-c/)的一些用例:

### **<u>限制鼠标指针</u> :**

鼠标指针可以限制在特定的矩形中。其思想是创建一个名为 **restrictmouse()** 的函数，该函数接受包含 X 坐标和 Y 坐标的四个参数。第一点提到矩形的顶部，第二点提到矩形的底部。下面是用于相同的功能:

*   **initmouse ():** is used to initialize the mouse.
*   **show mouse ():** Display the mouse pointer on the output screen.
*   **RestrictMouse ():** Used to set the horizontal and vertical limits of the mouse pointer by setting the following parameters. **AX = 7** horizontally, and **AX = 8** vertically.

下面是同样的程序:

## C

T5

```cpp
// C program to restrict the mouse
// pointer
#include <conio.h>
#include <dos.h>
#include <graphics.h>
#include <stdio.h>
union REGS in, out;

// Function to initialize the mouse
// pointer using graphics
int initMouse()
{
    in.x.ax = 0;
    int86(0X33, &in, &out);

    return out.x.ax;
}

// Function to display the mouse
// pointer using graphics
void showMouse()
{
    in.x.ax = 1;
    int86(0X33, &in, &out);
}

// Function to restrict the mouse
// pointers
void restrictMouse(int x1, int y1,
                   int x2, int y2)
{
    // Set Horizontal limit
    in.x.ax = 7;
    in.x.cx = x1;
    in.x.dx = x2;
    int86(0X33, &in, &out);

    // Set Vertical limit
    in.x.ax = 8;
    in.x.cx = y1;
    in.x.dx = y2;
    int86(0X33, &in, &out);
}

// Driver Code
void main()
{
    int status, i, gd = DETECT, gm;

    // Initialize graphics
    initgraph(&gd, &gm, "C:\\TURBOC3\\BGI");

    // Get the status of the mouse
    status = initMouse();

    // Check if mouse is available or not
    if (status == 0)
        printf("Mouse support "
               "not available.\n");
    else {
        showMouse();

        // Draw rectangle for displaying
        // the boundary
        rectangle(100, 70, 400, 200);
        restrictMouse(100, 70, 400, 200);
    }
    getch();

    // Close the graphics
    closegraph();

    return 0;
}
```