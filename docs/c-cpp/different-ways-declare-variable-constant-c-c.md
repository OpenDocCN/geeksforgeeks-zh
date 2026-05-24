# 在 C 和 C++ 中将变量声明为常量的不同方式

> 原文:[https://www . geesforgeks . org/different-way-declare-variable-constant-c-c/](https://www.geeksforgeeks.org/different-ways-declare-variable-constant-c-c/)

有许多不同的方法使变量成为常数

1.  **使用 [const 关键字](https://www.geeksforgeeks.org/const-qualifier-in-c/):**const 关键字指定变量或对象值是常量，在编译时不能修改。

    ```cpp
    // C program to demonstrate const specifier
    #include <stdio.h>
    int main()
    {
        const int num = 1;

        num = 5; // Modifying the value
        return 0;
    }
    ```

    ```cpp
    It will throw as error like:
    error: assignment of read-only variable ‘num’

    ```

2.  **Using [enum keyword](https://www.geeksforgeeks.org/enumeration-enum-c/):** Enumeration (or enum) is a user defined data type in C and C++. It is mainly used to assign names to integral constants, that make a program easy to read and maintain.

    ```cpp
    // In C and C++ internally the default
    // type of 'var' is int
    enum VARS { var = 42 };

    // In C++ 11 (can have any integral type):
    enum : type { var = 42; }

    // where mytype = int, char, long etc.
    // but it can't be float, double or
    // user defined data type.
    ```

    **注意:****枚举**的数据类型当然是有限的，正如我们在上面的例子中看到的。

3.  **Using [constexpr](https://www.geeksforgeeks.org/understanding-constexper-specifier-in-c/) keyword:** Using constexpr in C++(not in C) can be used to declare variable as a guaranteed constant. But it would fail to compile if its initializer isn’t a constant expression.

    ```cpp
    #include <iostream>

    int main()
    {
        int var = 5;
        constexpr int k = var;
        std::cout << k;
        return 0;
    }
    ```

    上述程序将抛出一个错误，

    ```cpp
    error: the value of ‘var’ is not usable in a constant expression
    ```

    因为变量“var”不是常量表达式。因此，为了使它成为常数，我们必须用 **const** 关键字声明变量“var”。

4.  **使用[宏](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/) :** 我们也可以使用宏来定义常量，但是有一个陷阱，

    ```cpp
    #define var 5
    ```