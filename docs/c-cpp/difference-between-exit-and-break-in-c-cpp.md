# C/c++ 中退出()和中断的区别

> 原文:[https://www . geesforgeks . org/c-CPP/](https://www.geeksforgeeks.org/difference-between-exit-and-break-in-c-cpp/)退出和闯入的区别

本文的主题是了解[退出()](https://www.geeksforgeeks.org/exit-vs-_exit-c-cpp/)和[打破](https://www.geeksforgeeks.org/break-statement-cc/)的区别。

[**退出()**](https://www.geeksforgeeks.org/exit-vs-_exit-c-cpp/) **:**

*   Use this function when the user wants to quit a program.
*   Is a void return function, which calls all functions registered at the exit and terminates the program.
*   Refresh the file buffer, close the stream, and delete the temporary file, thus freeing memory.

**语法:**

```cpp
void exit(int status);
```

使用的参数如下:

<figure class="table">T21】

| **值** | **描述** |
| --- | --- |
| EXIT _ SUCCESS | 成功终止 |
| 0 | 成功终止 |
| EXIT _ fail | 不成功终止 |

</figure>

[**break()**](https://www.geeksforgeeks.org/break-statement-cc/)**:**

*   This function is generally used to generate a [loop](https://www.geeksforgeeks.org/loops-in-c-and-cpp/) in an instant.
*   When a break statement is executed, it transfers control to the statement that follows the switch or loop.

**语法:**

```cpp
break;
```

### **<u>两个功能之间的表格差异</u> :**

<figure class="table">

| **break()** | **exit()** |
| --- | --- |
| 它是一个关键字 | 它是一个预定义的函数。 |
| 它不需要任何头文件。 | 它需要头文件 stdlib.h |
| 它终止循环。 | 终止程序。 |
| 它通常只用于循环和开关情况内的语句。 | 它经常在程序中的任何地方使用。 |
| 不能作为变量名，因为它是 [C 语言](https://www.geeksforgeeks.org/c-language-set-1-introduction/)中的保留字。 | 它不是一个保留字所以，它经常被用作变量名。 |
| 在一个 C 程序中，可以执行多个 **break** 语句。 | 在一个 C 程序中，只会执行一个退出功能。 |

</figure>

**程序 1:**

下面是一个 [C 程序](https://www.geeksforgeeks.org/c/)演示使用 break:

## c++

```cpp
// C++ program to demonstrate the use
// of break statement
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Local variable definition
    int a = 10;

    // While loop execution
    while (a < 20) {

        cout <<"value of a:"<< a<< endl;
        a++ ;

        // terminate the loop using
        // break statement
        if (a > 15) {
            break;
        }
    }

    cout <<"The break statement executed"
           " when when the value "
           " became "<< a;

    return 0;
}

//this code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to demonstrate the use
// of break statement
#include <stdio.h>

// Driver Code
int main()
{
    // Local variable definition
    int a = 10;

    // While loop execution
    while (a < 20) {

        printf("value of a: %d\n", a);
        a++ ;

        // terminate the loop using
        // break statement
        if (a > 15) {
            break;
        }
    }

    printf("The break statement executed"
           " when when the value "
           " became %d\n",
           a);

    return 0;
}
```

**输出:**

```cpp
value of a: 10
value of a: 11
value of a: 12
value of a: 13
value of a: 14
value of a: 15
The break statement executed when when the value  became 16
```

**说明:**在上述代码中，当满足 if 条件时，break 终止 while 循环，此后的代码 while 循环将在中断循环后执行。

**程序 2:**

下面是演示 exit()用法的 C 程序:

## c++

```cpp
// C++ program to demonstrate the
// use of exit()
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    for (int i = 1; i < 5; i++) {
        if (i == 3)
            exit(0);
        cout <<"i = "<< i << "\n";
    }

    for (int j = 9; j > 0; j--) {
        if (j == 5)
            cout <<"j = "<< j;
    }

    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to demonstrate the
// use of exit()
#include <stdio.h>
#include <stdlib.h>

// Driver Code
int main()
{
    for (int i = 1; i < 5; i++) {
        if (i == 3)
            exit(0);
        printf("i = %d \t", i);
    }

    printf("\n");

    for (int j = 9; j > 0; j--) {
        if (j == 5)
            printf("j = %d \t", j);
    }

    return 0;
}
```

**输出:**

```cpp
i = 1     i = 2
```

**说明:**在上面的代码中，退出函数执行后，程序终止，之后没有代码执行。