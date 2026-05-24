# 关于 C/C++ 中数据类型和修饰符的有趣事实

> 原文:[https://www . geesforgeks . org/interior-facts-about-data-type-and-modifiers-in-c-CPP/](https://www.geeksforgeeks.org/interesting-facts-about-data-types-and-modifiers-in-c-cpp/)

以下是一些关于数据类型和与数据类型相关的修饰符的逻辑和有趣的事实

**1。**如果没有给变量赋予数据类型，编译器会自动将其转换为 int 数据类型。

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    signed a;
    signed b;

    // size of a and b is equal to the size of int
    cout << "The size of a is " << sizeof(a) <<endl; 
    cout << "The size of b is " << sizeof(b); 
    return (0);
}

// This code is contributed by shubhamsingh10
```

## C

```cpp
#include <stdio.h>
int main()
{
    signed a;
    signed b;

    // size of a and b is equal to the size of int
    printf("The size of a is %d\n", sizeof(a)); 
    printf("The size of b is %d", sizeof(b)); 
    return (0);
}
```

Output:

```cpp
The size of a is 4
The size of b is 4

```

**2。**有符号是 char 和 int 数据类型的默认修饰符。

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    int x;
    char y;
    x = -1;
    y = -2;
    cout << "x is "<< x <<" and y is " << y << endl;
}

// This code is contributed by shubhamsingh10
```