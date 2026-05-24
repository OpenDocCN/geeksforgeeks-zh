# 一边(1)一边(2)哪个更快？

> 原文:[https://www . geeksforgeeks . org/while 1 或 while2/](https://www.geeksforgeeks.org/which-will-be-faster-while1-or-while2/) 哪个会更快

在大多数编程语言中， [while 循环](https://www.geeksforgeeks.org/c-c-while-loop-with-examples/)是一种控制流语句，它允许基于给定的布尔条件重复执行代码。布尔条件要么是**真**要么是**假**。

**而(1) &而(2)**

这是一个无限循环，将一直运行到一个 break 语句被显式发出。 **while(1)** 和 **while(2)** 但任何非零的整数都不会产生与 while(1)类似的效果。因此，while(1)、while(2)或 while(-255)，都只会给出无限循环，除非我们使用 break 语句。

```cpp
while(1) or while(2) or while(any non-zero integer)
{ 
    // loop runs infinitely
}

```

但实际上，在现实世界中使用 **while(1)或 while(任何非零整数)**是不可取的，因为它增加了 CPU 的使用，并且还会阻塞代码，即在程序手动关闭之前，不能从 **while(1)** 中出来。**而(1)** 可以用在条件总是需要真实的地方。

下面是在 C/C++ 中说明 while(1)和 while(2)的代码:

**节目 1:**

## C

```cpp
// C program to illustrate while(1)
#include<stdio.h>

// Driver Code
int main()
{
    int i = 0;
    while (1) {

        printf("%d ", ++ i);
        if (i == 5) {

            // Break to come out of loop
            break;
        }
    }
    return 0;
}
```

## C++

```cpp
// C++ program to illustrate while(1)
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int i = 0;
    while (1) {

        cout << ++ i << " ";
        if (i == 5) {

            // Break to come out of loop
            break;
        }
    }
    return 0;
}
```

**Output:**

```cpp
1 2 3 4 5

```

**节目 2:**

## C

```cpp
// C program to illustrate while(2)
#include<stdio.h>

// Driver Code
int main()
{
    int i = 0;
    while (2) {

        printf("%d ", ++ i);
        if (i == 5) {

            // Break to come out of loop
            break;
        }
    }
    return 0;
}
```

## C++

```cpp
// C++ program to illustrate while(2)
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int i = 0;
    while (2) {

        cout << ++ i << " ";
        if (i == 5) {

            // Break to come out of loop
            break;
        }
    }
    return 0;
}
```

**Output:**

```cpp
1 2 3 4 5

```