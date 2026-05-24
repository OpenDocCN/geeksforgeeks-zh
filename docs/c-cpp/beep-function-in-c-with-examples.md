# C 中的哔哔声()功能，示例

> 原文:[https://www . geesforgeks . org/beep-function-in-c-with-examples/](https://www.geeksforgeeks.org/beep-function-in-c-with-examples/)

C 中的**哔声功能**用来发出哔声。它会在扬声器上产生音调。这个函数是同步的，也就是说，它会等待，直到声音结束才返回到它的调用者函数。在[调试过程中](https://www.geeksforgeeks.org/software-engineering-debugging/)发现错误非常有用。
**头文件:**

```cpp
#include <windows.h>

```

**语法:**

```cpp
BEEP(x, y)

```

**参数:**该方法接受两个参数:

*   **x** :声音的频率是多少
*   **y** :持续时间，单位为毫秒，直到声音打开。

**返回类型:**

*   如果函数产生声音，那么它返回任何非零值。
*   如果函数不产生声音，那么它返回零。

以下是 **BEEP()** 功能说明:
**程序 1:**

## C

```cpp
// C program to illustrate BEEP() function

#include <stdio.h>
#include <windows.h>

// Driver Code
int main()
{

    // Function that beeps a sound of
    // frequency 750 for 0.8 sec
    BEEP(750, 800);

    getch();
    return 0;
}
```

**注意:**程序在联机 IDE 中不会产生声音。请尝试在脱机编译器中运行它。
**节目 2:**

## C

```cpp
// C program to play song Jingle Bell
// using the BEEP() function

#include <stdio.h>
#include <windows.h>

// Driver Code
int main()
{
    int x;

    // Loop for sound Jingle
    for (x = 0; x < 2; x++) {
        Beep(523, 500);
    }

    // sound Bell
    Beep(523, 800);

    Sleep(200);

    // Loop for sound Jingle
    for (x = 0; x < 2; x++) {
        Beep(523, 500);
    }

    // sound Bell
    Beep(523, 800);

    // Sound for rest of the tone
    Sleep(200);

    Beep(523, 500);

    Sleep(50);

    Beep(659, 400);

    Sleep(50);

    Beep(440, 400);

    Sleep(50);

    Beep(494, 400);

    Sleep(50);

    Beep(523, 750);

    Sleep(400);

    Beep(600, 400);

    Sleep(100);

    Beep(600, 350);

    Sleep(200);

    Beep(600, 300);

    Sleep(150);

    Beep(600, 250);

    Sleep(150);

    Beep(600, 150);

    Sleep(150);

    Beep(550, 250);

    Sleep(150);

    Beep(555, 350);

    Sleep(50);

    Beep(555, 200);
    Sleep(150);

    Beep(555, 200);

    Sleep(150);

    Beep(690, 200);

    Sleep(150);

    Beep(690, 200);

    Sleep(150);

    Beep(610, 200);

    Sleep(150);

    Beep(535, 160);

    Sleep(100);

    Beep(500, 150);

        Beep(500, 50);

    Sleep(200);

    Beep(700, 200);

    return 0;
}
```