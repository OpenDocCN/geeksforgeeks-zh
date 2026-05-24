# 点(。)C/C++ 中的运算符

> 原文:[https://www.geeksforgeeks.org/dot-operator-in-c-c/](https://www.geeksforgeeks.org/dot-operator-in-c-c/)

**点(。)运算符**用于通过对象名称进行**直接成员选择**。换句话说，它用于访问子对象。

**语法:**

```cpp
object.member;
```

**例如:**

```cpp
#include <stdio.h>

struct Point {
    int x, y;
};

int main()
{
    struct Point p1 = { 0, 1 };

    // Accessing members of point p1
    // using the dot operator
    p1.x = 20;

    printf("x = %d, y = %d", p1.x, p1.y);

    return 0;
}
```

**输出:**

```cpp
x = 20, y = 1

```