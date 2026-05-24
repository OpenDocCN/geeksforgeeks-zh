# getch()函数在 C 中用例子

> 原文:[https://www . geesforgeks . org/getch-function-in-c-with-examples/](https://www.geeksforgeeks.org/getch-function-in-c-with-examples/)

**getch()** 是一个**非标准函数**，存在于 [**conio.h 头文件**](http://en.wikipedia.org/wiki/Conio.h) **文件**中，该文件主要由 [MS-DOS 编译器使用，如 Turbo C](https://www.geeksforgeeks.org/editors-types-system-programming/) 。它不是 C 标准库或 ISO C 的**部分，也不是 POSIX 定义的。
像[这些功能](https://www.geeksforgeeks.org/difference-getchar-getch-getc-getche/)一样，getch()也从键盘上读取单个字符。但是它不使用任何缓冲区，所以输入的字符会立即返回，而无需等待回车键。
**语法:**** 

```cpp
int getch(void);
```

**参数:**此方法不接受任何参数。
**返回值:**该方法返回按键的 ASCII 值。
**例:**

## C

```cpp
// Example for getch() in C

#include <stdio.h>

// Library where getch() is stored
#include <conio.h>

int main()
{
    printf("%c", getch());
    return 0;
}
```

```cpp
Input:  g (Without enter key)
Output: Program terminates immediately.
        But when you use DOS shell in Turbo C, 
        it shows a single g, i.e., 'g'
```

**关于 getch()方法的要点:**T2】

1.  getch()方法暂停输出控制台，直到按下某个键。
2.  它不使用任何缓冲区来存储输入字符。
3.  输入的字符会立即返回，无需等待回车键。
4.  输入的字符不会显示在控制台上。
5.  getch()方法可用于接受隐藏的输入，如密码、自动柜员机个人识别码等。

**示例:使用 getch()**
**接受隐藏密码注意:**下面的代码不会在 Online 编译器上运行，而是在像 Turbo IDE 这样的 MS-DOS 编译器上运行。

## C

```cpp
// C code to illustrate working of
// getch() to accept hidden inputs

#include <conio.h>
#include <dos.h> // delay()
#include <stdio.h>
#include <string.h>

void main()
{

    // Taking the password of 8 characters
    char pwd[9];
    int i;

    // To clear the screen
    clrscr();

    printf("Enter Password: ");
    for (i = 0; i < 8; i++) {

        // Get the hidden input
        // using getch() method
        pwd[i] = getch();

        // Print * to show that
        // a character is entered
        printf("*");
    }
    pwd[i] = '\0';
    printf("\n");

    // Now the hidden input is stored in pwd[]
    // So any operation can be done on it

    // Here we are just printing
    printf("Entered password: ");
    for (i = 0; pwd[i] != '\0'; i++)
        printf("%c", pwd[i]);

    // Now the console will wait
    // for a key to be pressed
    getch();
}
```

**输出:**

```cpp
Abcd1234
```

**输出:**

```cpp
Enter Password: ********
Entered password: Abcd1234
```