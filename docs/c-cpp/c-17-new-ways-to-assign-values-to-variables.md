# C++ 17 |给变量赋值的新方法

> 原文:[https://www . geesforgeks . org/c-17-变量赋值新方法/](https://www.geeksforgeeks.org/c-17-new-ways-to-assign-values-to-variables/)

C++ 17 引入了许多新的方法来声明变量。先前的赋值和声明是使用“=”完成的

示例:

```cpp
int a = 5;

```

但是现在在 **C++ 17** 中又引入了 2 种方式。它们是:

1.  **Constructor initialization:** In this way, the value of the variable is enclosed in parentheses ( () ). In this way, value can be passed in two ways shown below.

    ```cpp
    #include <iostream>
    using namespace std;

    // Driver Code
    int main()
    {

        // Declaring the variable in parentheses
        // Method 1
        int a(5);
        cout << "a = " << a;

        // Declaring the variable in parentheses
        // Method 2
        int b = (10);
        cout << endl
             << "b = " << b;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    a = 5
    b = 10

    ```

    **解释**
    在 C++ 17 中，变量也可以通过括号提供值来声明。构造函数初始化和旧的正常初始化方式的区别在于，无论大小或符号是什么，它总是返回括号中的最后一个值。

    例如，

    ```cpp
    a=(2, 21, -50, 1)
    ```

    存储在中的值将是 1。

2.  **Uniform initialization:** In this way, the value of the variable is enclosed in curly braces ( {} ) instead of parentheses. In this way, the value can be passed in two ways shown below.

    ```cpp
    #include <iostream>
    using namespace std;

    int main()
    {

        // Declaring the variable in curly braces
        // Method 1
        int a{ 3 };
        cout << "a = " << a;

        // Declaring the variable in curly braces
        // Method 2
        int b = { 7 };
        cout << endl
             << "b = " << b;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    a = 3
    b = 7

    ```

    与构造函数初始化不同，此赋值方法只能接受大括号中的一个值。提供多个值将返回编译错误。

    例如，

    ```cpp
    int b={7, 12};

    ```

    **输出**

    ```cpp
    prog.cpp: In function 'int main()':
    prog.cpp:9:12: error: scalar object 'b' requires one element in initializer
     int b={7, 12};
                ^

    ```