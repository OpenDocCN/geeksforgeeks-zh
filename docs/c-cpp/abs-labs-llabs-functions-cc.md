# abs()，labs()，llabs()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/abs-labs-llabs-functions-cc/](https://www.geeksforgeeks.org/abs-labs-llabs-functions-cc/)

abs()、labs()、llabs()函数在 **cstdlib** 头文件中定义。这些函数返回作为参数输入的整数的绝对值。

1.  **abs()函数:**该函数的输入是 C 语言中类型 *int* 的值和 C++ 语言中类型 *int* 、 *long int* 或 *long long int* 的值。在 C 中，输出为 *int* 类型，在 C++ 中，输出与输入具有相同的数据类型。
    下面是展示 abs()函数工作原理的 C++ 示例程序。

    ```cpp
    // CPP program to illustrate
    // abs() function
    #include <cstdlib>
    #include <iostream>

    using namespace std;

    int main()
    {
        int val1, val2;

        /// finding absolute value using
        /// abs() function.
        val1 = abs(22);
        val2 = abs(-43);

        cout << "abs(22) = " << val1 << "\n";
        cout << "abs(-43) = " << val2 << "\n";
        return 0;
    }
    ```

    ```cpp
    Output: 
    abs(22) = 22
    abs(-43) = 43

    ```

2.  **labs()函数:**这是 abs()函数的长 int 版本。输入输出均为*长整型*型。
    下面是展示 labs()函数工作的 C++ 示例程序。

    ```cpp
    // CPP program to illustrate
    // labs() function
    #include <cstdlib>
    #include <iostream>

    using namespace std;

    int main()
    {
        int val1, val2;

        /// finding absolute value using
        /// labs() function.
        val1 = labs(1234355L);
        val2 = labs(-4325600L);

        cout << "labs(1234355L) = " << val1 << "\n";
        cout << "labs(-4325600L) = " << val2 << "\n";
        return 0;
    }
    ```

    ```cpp
    Output: 
    labs(1234355L) = 1234355
    labs(-4325600L) = 4325600

    ```

3.  **llabs()函数:**这是长 int 版的 abs()函数。输入输出均为*长整型*型。
    下面是展示 llabs()函数工作的 C++ 示例程序。

    ```cpp
    // CPP program to illustrate
    // llabs() function
    #include <cstdlib>
    #include <iostream>

    using namespace std;

    int main()
    {
        int val1, val2;

        /// finding absolute value using
        /// labs() function.
        val1 = llabs(1234863551LL);
        val2 = llabs(-432592160LL);

        cout << "llabs(1234863551LL) = " << val1 << "\n";
        cout << "llabs(-432592160LL) = " << val2 << "\n";
        return 0;
    }
    ```

    ```cpp
    Output: 
    llabs(1234863551LL) = 1234863551
    llabs(-432592160LL) = 432592160

    ```