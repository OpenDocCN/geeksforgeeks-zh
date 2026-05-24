# C/c++ 中实参和参数的区别举例

> 原文:[https://www . geeksforgeeks . org/c-c-in-parameter-with-examples/](https://www.geeksforgeeks.org/difference-between-argument-and-parameter-in-c-c-with-examples/)

**参数**

**参数**是指调用函数时在函数内传递的值。这些值通常是在执行过程中需要参数的函数的来源。这些值被分配给被调用函数定义中的变量。函数中传递的值的类型与函数定义中定义的变量的类型相同。这些也被称为**实际参数**或**实际参数**。

**例:**假设需要调用 sum()函数，两个数相加。这两个数字被称为参数，并在从其他地方调用 sum()时传递给它。

## C

```cpp
// C code to illustrate Arguments

#include <stdio.h>

// sum: Function definition
int sum(int a, int b)
{
    // returning the addition
    return a + b;
}

// Driver code
int main()
{
    int num1 = 10, num2 = 20, res;

    // sum() is called with
    // num1 & num2 as ARGUMENTS.
    res = sum(num1, num2);

    // Displaying the result
    printf("The summation is %d", res);
    return 0;
}
```

## c++

```cpp
// C++ code to illustrate Arguments
#include <iostream>
using namespace std;

// sum: Function definition
int sum(int a, int b)
{
    // returning the addition
    return a + b;
}

// Driver code
int main()
{
    int num1 = 10, num2 = 20, res;

    // sum() is called with
    // num1 & num2 as ARGUMENTS.
    res = sum(num1, num2);

    // Displaying the result
    cout << "The summation is " << res;
    return 0;
}
```

**输出:**

```cpp
The summation is 30

```