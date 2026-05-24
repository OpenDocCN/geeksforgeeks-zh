# 切片()功能在 C

> 原文:[https://www.geeksforgeeks.org/pieslice-function-c/](https://www.geeksforgeeks.org/pieslice-function-c/)

**pieslice()** 绘制并填充中心位于(x，y)且半径为 r 的饼图切片。切片从 s_angle 移动到 e_angle，这是饼图切片的开始和结束角度。饼图切片的角度以度为单位，逆时针测量。

**语法:**

```cpp
void pieslice(int x, int y, int s_angle, 
                    int e_angle, int r);

where,
(x, y) is center of the circle.
r is the radius of the circle.
s_angle and e_angle are the starting 
and ending angles respectively.

```

**示例:**

```cpp
Input : x = 300, y = 300, s_angle = 0 ,
        e_angle = 120, r = 150
Output :

Input : x = 300, y = 300, s_angle = 30 ,
        e_angle = 100, r = 200
Output :

```

下面是 pieslice()函数的实现:

```cpp
// C Implementation for drawing pieslice
#include <graphics.h>

// driver code
int main()
{
    // gm is Graphics mode which 
    // is a computer display mode 
    // that generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm;

    // initgraph initializes the 
    // graphics system by loading a 
    // graphics driver from disk
    initgraph(&gd, &gm, "");

    // pieslice function
    pieslice(300, 300, 0, 120, 150);

    getch();

    // closegraph function closes the 
    // graphics mode and deallocates all 
    // memory allocated by graphics system .
    closegraph();

    return 0;
}
```

输出: