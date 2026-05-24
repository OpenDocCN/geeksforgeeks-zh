# c++ 中的类型转换

> 原文:[https://www.geeksforgeeks.org/type-conversion-in-c/](https://www.geeksforgeeks.org/type-conversion-in-c/)

类型转换基本上是从一种类型到另一种类型的转换。有两种类型的类型转换:

1.  **Implicit Type Conversion** Also known as ‘automatic type conversion’.
    *   由编译器自行完成，无需用户的任何外部触发。
    *   通常在表达式中存在多个数据类型时发生。在这种情况下，进行类型转换(类型提升)以避免数据丢失。
    *   变量的所有数据类型都升级为数据类型最大的变量的数据类型。

        ```cpp
        bool -> char -> short int -> int -> 

        unsigned int -> long -> unsigned -> 

        long long -> float -> double -> long double

        ```

    *   隐式转换可能会丢失信息，符号可能会丢失(当有符号隐式转换为无符号时)，并且可能会发生溢出(当 long long 隐式转换为 float 时)。

    **类型隐式转换示例:**

    ```cpp
    // An example of implicit conversion

    #include <iostream>
    using namespace std;

    int main()
    {
        int x = 10; // integer x
        char y = 'a'; // character c

        // y implicitly converted to int. ASCII
        // value of 'a' is 97
        x = x + y;

        // x is implicitly converted to float
        float z = x + 1.0;

        cout << "x = " << x << endl
             << "y = " << y << endl
             << "z = " << z << endl;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    x = 107
    y = a
    z = 108

    ```

2.  **Explicit Type Conversion**: This process is also called type casting and it is user-defined. Here the user can typecast the result to make it of a particular data type.

    在 C++ 中，可以通过两种方式完成:

    *   **Converting by assignment:** This is done by explicitly defining the required type in front of the expression in parenthesis. This can be also considered as forceful casting.

        **语法:**

        ```cpp
        (type) expression
        ```

        其中*类型*表示最终结果转换到的数据类型。

        **示例:**

        ```cpp
        // C++ program to demonstrate
        // explicit type casting

        #include <iostream>
        using namespace std;

        int main()
        {
            double x = 1.2;

            // Explicit conversion from double to int
            int sum = (int)x + 1;

            cout << "Sum = " << sum;

            return 0;
        }
        ```

        **Output:**

        ```cpp
        Sum = 2

        ```

    *   **使用 Cast 运算符的转换:**Cast 运算符是一个**一元运算符**，它强制将一种数据类型转换为另一种数据类型。
        C++ 支持四种类型的铸造:
        1.  [静态铸造](https://www.geeksforgeeks.org/static_cast-in-c-type-casting-operators/)
        2.  动态铸造
        3.  [Const Cast](https://www.geeksforgeeks.org/casting-operators-in-c-set-1-const_cast/)
        4.  [重新诠释演员表](https://www.geeksforgeeks.org/reinterpret_cast-in-cpp/)

            **示例:**

            ```cpp
            #include <iostream>
            using namespace std;
            int main()
            {
                float f = 3.5;

                // using cast operator
                int b = static_cast<int>(f);

                cout << b;
            }
            ```

            **Output:**

            ```cpp
            3

            ```

**类型转换的优势:**

*   这样做是为了利用类型层次结构或类型表示的某些特性。
*   它有助于计算包含不同数据类型变量的表达式。