# C/c++ 中鼠标编程用例

> 原文:[https://www . geesforgeks . org/c-c 中鼠标编程用例/](https://www.geeksforgeeks.org/use-cases-of-mouse-programming-in-c-c/)

在本文中，我们将讨论[鼠标编程](https://www.geeksforgeeks.org/mouse-programming-in-c-c/)的一些用例:

### **<u>在</u>** [**<u>图形模式</u>**](https://www.geeksforgeeks.org/basic-graphic-programming-in-c/) **:**

要显示鼠标指针，首先使用 **initgraph()** 函数启用图形模式，如果初始化成功，则调用 **initMouse()** 函数检查鼠标是否可用，如果 **initMouse()** 函数返回**不等于 0，则返回 ffffh** ，然后调用 **showMouse()** 函数，[在图形模式下将光标显示在控制台窗口](https://www.geeksforgeeks.org/how-to-get-the-current-position-of-cursor-from-output-screen-in-c/)上。下面是使用的函数:

*   ***initmouse ():*** Used to initialize the mouse.
*   ***show mouse ():*** Display the mouse pointer on the output screen.

下面是同样的程序:

## C

T5

```cpp
// C program to display Mouse
// pointer in Graphics Mode
#include <conio.h>
#include <dos.h>
#include <graphics.h>
#include <stdio.h>
union REGS in, out;

// Function to display the mouse
// pointer
void showMouse()
{
    // Set service AX = 1 for
    // displaying mouse
    in.x.ax = 1;
    int86(0X33, &in, &out);
}

// Function to initialize the mouse
// pointer
int initMouse()
{
    // Set service AX = 0 for
    // detecting mouse
    in.x.ax = 0;
    int86(0x33, &in, &out);
    return out.x.ax;
}

// Driver Code
void main()
{
    int status, gd = DETECT, gm;
    clrscr();

    initgraph(&gd, &gm,
              "C:\\TURBOC3\\BGI");

    // Get the status of mouse pointer
    status = initMouse();

    // Check mouse is available or not
    if (status == 0)
        printf("Mouse support not"
               " available.\n");
    else {
        printf("Display mouse");
        showMouse();
    }

    getch();

    // Close the graphics
    closegraph();
}
```