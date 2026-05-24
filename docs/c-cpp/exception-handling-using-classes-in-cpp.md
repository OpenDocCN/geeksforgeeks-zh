# 使用 C++ 中的类处理异常

> 原文:[https://www . geesforgeks . org/异常处理-使用类-in-cpp/](https://www.geeksforgeeks.org/exception-handling-using-classes-in-cpp/)

在本文中，我们将讨论如何使用[类](https://www.geeksforgeeks.org/c-classes-and-objects/)处理异常。

**异常处理:**

*   [异常](https://www.geeksforgeeks.org/exception-handling-c/)是程序在执行过程中遇到的运行时异常或异常情况。
*   有两种类型的例外:
    *   同步异常
    *   异步异常(例如:程序无法控制的异常、磁盘故障等)。
*   C++ 为此提供了以下专用关键字:
    *   [**试试**](https://www.geeksforgeeks.org/try-catch-throw-and-throws-in-java/) **:** 代表可以抛出异常的一段代码。
    *   [**catch**](https://www.geeksforgeeks.org/try-catch-throw-and-throws-in-java/) **:** 表示当抛出特定异常时执行的代码块。
    *   [**抛出**](https://www.geeksforgeeks.org/try-catch-throw-and-throws-in-java/) **:用来抛出一个异常。也用于列出函数抛出但不处理自身的异常。**

**问题陈述:**

*   创建一个有两个数据成员 **a** 和 **b** 的类号。
*   写迭代函数求两个数的 [GCD。](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/)
*   写一个迭代函数来检查任何给定的数是否是质数。如果发现**为真**，则向类**抛出异常**。
*   定义自己的 **MyPrimeException** 类。

**解决方案:**

*   定义一个名为 **Number** 的类，它有两个私有数据成员，分别是 **a** 和 **b** 。
*   将两个成员函数定义为:
    *   **int gcd():** 到[计算两个数](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/)的 HCF。
    *   **bool isPrime():** 至[检查给定的数字是否为质数](https://www.geeksforgeeks.org/prime-numbers/)。
*   使用[构造函数](https://www.geeksforgeeks.org/constructors-c/)，用于初始化数据成员。
*   以另一个名为**临时**的类为例，当抛出异常时将调用该类。

下面是使用类来说明[](https://www.geeksforgeeks.org/comparison-of-exception-handling-in-c-and-java/)**异常处理概念的实现:**

## **C++**

```cpp
// C++ program to illustrate the concept
// of exception handling using class

#include <bits/stdc++.h>
using namespace std;

// Class declaration
class Number {
private:
    int a, b;

public:
    // Constructors
    Number(int x, int y)
    {
        a = x;
        b = y;
    }

    // Function that find the GCD
    // of two numbers a and b
    int gcd()
    {
        // While a is not equal to b
        while (a != b) {

            // Update a to a - b
            if (a > b)
                a = a - b;

            // Otherwise, update b
            else
                b = b - a;
        }

        // Return the resultant GCD
        return a;
    }

    // Function to check if the
    // given number is prime
    bool isPrime(int n)
    {
        // Base Case
        if (n <= 1)
            return false;

        // Iterate over the range [2, N]
        for (int i = 2; i < n; i++) {

            // If n has more than 2
            // factors, then return
            // false
            if (n % i == 0)
                return false;
        }

        // Return true
        return true;
    }
};

// Empty class
class MyPrimeException {
};

// Driver Code
int main()
{
    int x = 13, y = 56;

    Number num1(x, y);

    // Print the GCD of X and Y
    cout << "GCD is = "
         << num1.gcd() << endl;

    // If X is prime
    if (num1.isPrime(x))
        cout << x
             << " is a prime number"
             << endl;

    // If Y is prime
    if (num1.isPrime(y))
        cout << y
             << " is a prime number"
             << endl;

    // Exception Handling
    if ((num1.isPrime(x))
        || (num1.isPrime(y))) {

        // Try Block
        try {
            throw MyPrimeException();
        }

        // Catch Block
        catch (MyPrimeException t) {

            cout << "Caught exception "
                 << "of MyPrimeException "
                 << "class." << endl;
        }
    }

    return 0;
}
```

****Output:**

```cpp
GCD is = 1
13 is a prime number
Caught exception of MyPrimeException class.

```**