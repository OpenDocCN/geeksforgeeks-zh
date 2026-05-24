# 如何在 C 中从输出屏幕获取光标的当前位置？

> 原文:[https://www . geeksforgeeks . org/如何从 c 中输出屏幕获取光标的当前位置/](https://www.geeksforgeeks.org/how-to-get-the-current-position-of-cursor-from-output-screen-in-c/)

给定的任务是从 c 语言的输出屏幕中获取光标的当前位置。

**方法:**C 语言中有一个预定义的函数 **wherex()** ，返回光标在当前输出屏幕中的 x 坐标。以及**why()**函数，返回当前输出屏幕中光标的 y 坐标。这两个功能都在 **conio.h** headerfile 中定义。

*   **wherex():** This method returns the horizontal position of the cursor.

    **语法:**

    ```cpp
    int wherex();
    ```

    **参数:**该方法不接受任何参数。

    **返回值:**这个方法返回一个 1 到 80 范围内的整数值，或者根据系统的屏幕大小。

*   **wherey():** This method returns the vertical position of the cursor.

    **语法:**

    ```cpp
    int wherey();
    ```

    **参数:**该方法不接受任何参数。

    **返回值:**这个方法返回一个 1 到 50 范围内的整数值，或者根据系统的屏幕大小。

**注:**此代码根据 turbo C。

**例 1:**

```cpp
// C program to get the current
// cursor position from output screen

#include <conio.h>
#include <stdio.h>

void main()
{
    clrscr();

    // print current location of x.
    printf("current location of x is:%d\n", wherex());

    // print the current location of y.
    print("currentlocation of y is:%d", wherey());

    getch();
}
```

**输出:**
![](img/9ddf3510e7b3763a49b1e7bd3771e43d.png)

**例 2:**

```cpp
// C program to get the current
// cursor position from output screen

#include <conio.h>
#include <stdio.h>

void main()
{
    clrscr();

    // takes the cursor to given coordinates
    // here at (10, 15).
    gotoxy(10, 15);

    // print current location of x.
    printf("current location of x is:%d\n", wherex());

    // print the current location of y.
    print("currentlocation of y is:%d", wherey());

    getch();
}
```

**输出:**
![](img/64db50e59aca016a534140e1f6ac2e3a.png)

**参考文献:**

*   [https://code-reference.com/c/conio.h/wherex](https://code-reference.com/c/conio.h/wherex)
*   [https://code-reference.com/c/conio.h/wherey](https://code-reference.com/c/conio.h/wherey)