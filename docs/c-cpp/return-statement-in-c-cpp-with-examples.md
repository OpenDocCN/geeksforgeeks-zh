# C/c++ 中的返回语句，示例

> 原文:[https://www . geesforgeks . org/return-statement-in-c-CPP-with-examples/](https://www.geeksforgeeks.org/return-statement-in-c-cpp-with-examples/)

**先决条件:** [在 C/C++ ](https://www.geeksforgeeks.org/functions-in-c/) 中的功能

**返回语句**将执行流程返回到[函数](https://www.geeksforgeeks.org/functions-in-c/)，从这里调用它。这个语句不一定需要任何条件语句。语句一执行，程序的**流程立即停止**并从调用它的地方返回控制。return 语句可以为 void 函数返回任何东西，也可以不返回任何东西，但是对于非 void 函数，必须返回一个返回值。

**语法:**

```cpp
return[expression];
```

[![](img/f8e39f6e28383908160945b860ff3612.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191128194949/CPP-return-statement.png) 
使用返回语句的方式有多种。下面提到的很少:

1.  **不返回值的方法:**在 C/C++ 中，当方法属于返回类型时，不能跳过返回语句。仅对于 void 类型，可以跳过 return 语句。
    *   **Not using return statement in void return type function:** When a function does not return anything, the void return type is used. So if there is a void return type in the function definition, then there will be no return statement inside that function (generally).

        **语法:**

        ```cpp
        void func()
        {
            .
            .
            .
        }

        ```

        **例:**

        ## C

        ```cpp
        // C code to show not using return
        // statement in void return type function

        #include <stdio.h>

        // void method
        void Print()
        {
            printf("Welcome to GeeksforGeeks");
        }

        // Driver method
        int main()
        {

            // Calling print
            Print();

            return 0;
        }
        ```

        ## C++

        ```cpp
        // C++ code to show not using return
        // statement in void return type function

        #include <iostream>
        using namespace std;

        // void method
        void Print()
        {
            printf("Welcome to GeeksforGeeks");
        }

        // Driver method
        int main()
        {

            // Calling print
            Print();

            return 0;
        }
        ```

        **Output:**

        ```cpp
        Welcome to GeeksforGeeks

        ```

    *   **Using return statement in void return type function:** Now the question arises, what if there is a return statement inside a void return type function? Since we know that, if there is a void return type in the function definition, then there will be no return statement inside that function. But if there is a return statement inside it, then also there will be no problem if the syntax of it will be:

        **正确语法:**

        ```cpp
        void func()
        {
            return;
        }

        ```

        该语法在函数中用作跳转语句，目的是中断函数的流程并跳出它。人们可以把它看作是在函数中使用的“ [break 语句](https://www.geeksforgeeks.org/break-statement-cc/)”的替代。

        **例:**

        ## C

        ```cpp
        // C code to show using return
        // statement in void return type function

        #include <stdio.h>

        // void method
        void Print()
        {
            printf("Welcome to GeeksforGeeks");

            // void method using the return statement
            return;
        }

        // Driver method
        int main()
        {

            // Calling print
            Print();
            return 0;
        }
        ```

        ## C++

        ```cpp
        // C++ code to show using return
        // statement in void return type function

        #include <iostream>
        using namespace std;

        // void method
        void Print()
        {
            printf("Welcome to GeeksforGeeks");

            // void method using the return statement
            return;
        }

        // Driver method
        int main()
        {

            // Calling print
            Print();
            return 0;
        }
        ```

        **Output:**

        ```cpp
        Welcome to GeeksforGeeks

        ```

        但是如果 return 语句试图在 void 返回类型函数中返回一个值，这将导致错误。

        **语法错误:**

        ```cpp
        void func()
        {
            return value;
        }

        ```

        **警告:**

        ```cpp
        warning: 'return' with a value, in function returning void

        ```

        **例:**

        ## C

        ```cpp
        // C code to show using return statement
        // with a value in void return type function

        #include <stdio.h>

        // void method
        void Print()
        {
            printf("Welcome to GeeksforGeeks");

            // void method using the return
            // statement to return a value
            return 10;
        }

        // Driver method
        int main()
        {

            // Calling print
            Print();
            return 0;
        }
        ```

        ## C++

        ```cpp
        // C++ code to show using return statement
        // with a value in void return type function

        #include <iostream>
        using namespace std;

        // void method
        void Print()
        {
            printf("Welcome to GeeksforGeeks");

            // void method using the return
            // statement to return a value
            return 10;
        }

        // Driver method
        int main()
        {

            // Calling print
            Print();

            return 0;
        }
        ```

        **Warnings:**

        ```cpp
        prog.c: In function 'Print':
        prog.c:12:9: warning: 'return' with a value, in function returning void
          return 10;
                 ^

        ```

2.  **Methods returning a value:** For methods that define a return type, the return statement must be immediately followed by the return value of that specified return type.

    **语法:**

    ```cpp
    return-type func()
    {
        return value;
    }

    ```

    **例:**

    ## C

    ```cpp
    // C code to illustrate Methods returning
    // a value using return statement

    #include <stdio.h>

    // non-void return type
    // function to calculate sum
    int SUM(int a, int b)
    {
        int s1 = a + b;

        // method using the return
        // statement to return a value
        return s1;
    }

    // Driver method
    int main()
    {
        int num1 = 10;
        int num2 = 10;
        int sum_of = SUM(num1, num2);
        printf("The sum is %d", sum_of);
        return 0;
    }
    ```

    ## C++

    ```cpp
    // C++ code to illustrate Methods returning
    // a value using return statement

    #include <iostream>
    using namespace std;

    // non-void return type
    // function to calculate sum
    int SUM(int a, int b)
    {
        int s1 = a + b;

        // method using the return
        // statement to return a value
        return s1;
    }

    // Driver method
    int main()
    {
        int num1 = 10;
        int num2 = 10;
        int sum_of = SUM(num1, num2);
        cout << "The sum is " << sum_of;
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The sum is 20

    ```