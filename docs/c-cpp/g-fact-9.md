# 运算符大小的操作数

> 原文:[https://www.geeksforgeeks.org/g-fact-9/](https://www.geeksforgeeks.org/g-fact-9/)

sizeof 运算符用于返回其操作数的大小，以字节为单位。该运算符始终位于其操作数之前。操作数可以是数据类型或表达式。让我们通过适当的例子来看看这两个操作数。

1.  **type-name**: The type-name must be specified in parentheses.

    ```cpp
    sizeof(type - name)
    ```

    我们来看看代码:

    ## C

    ```cpp
    #include <stdio.h> 
    int main() 
    { 
        printf("%lu\n", sizeof(char)); 
        printf("%lu\n", sizeof(int)); 
        printf("%lu\n", sizeof(float)); 
        printf("%lu", sizeof(double));
        return 0; 
    } 
    ```

    ## C++

    ```cpp
    #include <iostream> 
    using namespace std; 

    int main() 
    { 
        cout << sizeof(char)<<"\n"; 
        cout << sizeof(int)<<"\n"; 
        cout << sizeof(float)<<"\n"; 
        cout << sizeof(double)<<"\n"; 
        return 0; 
    } 
    ```

    **Output:**

    ```cpp
    1
    4
    4
    8

    ```

2.  **expression**: The expression can be specified with or without the parentheses.

    ```cpp
    // First type
    sizeof expression

    // Second type
    sizeof(expression)
    ```

    表达式仅用于获取操作数的类型，而不用于计算。例如，下面的代码将 I 的值打印为 5，I 的大小为

    ## C

    ```cpp
    #include <stdio.h>

    int main()
    {
        int i = 5;
        int int_size = sizeof(i++);

        // Displaying the size of the operand
        printf("\n size of i = %d", int_size);

        // Displaying the value of the operand
        printf("\n Value of i = %d", i);

        getchar();
        return 0;
    }
    ```

    ## C++

    ```cpp
    #include <iostream>
    using namespace std;

    int main()
    {
        int i = 5;
        int int_size = sizeof(i++);

        // Displaying the size of the operand
        cout << "\n size of i = " << int_size;

        // Displaying the value of the operand
        cout << "\n Value of i = " << i;

        return 0;
    }

    // This code is contributed by SHUBHAMSINGH10
    ```

    **Output:**

    ```cpp
    size of i = 4
     Value of i = 5

    ```

**参考文献:**
[http://www . GNU . org/software/GNU-c-manual/GNU-c-manual . html # The-sizeof-Operator](http://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html#The-sizeof-Operator)