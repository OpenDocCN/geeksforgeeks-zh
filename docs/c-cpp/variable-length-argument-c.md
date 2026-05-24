# C 中的变长变元

> 原文:[https://www.geeksforgeeks.org/variable-length-argument-c/](https://www.geeksforgeeks.org/variable-length-argument-c/)

可变长度参数是一个允许函数接收任意数量参数的特性。有些情况下，我们希望一个函数根据需求处理可变数量的参数。
1)给定数字的和。
2)给定数量的最小值。
还有更多。

可变数量的参数由三个点(…)表示

下面是一个例子，求给定整数集的最小值。

```cpp
// C program to demonstrate use of variable
// number of arguments.
#include <stdarg.h>
#include <stdio.h>

// this function returns minimum of integer
// numbers passed.  First argument is count
// of numbers.
int min(int arg_count, ...)
{
    int i;
    int min, a;

    // va_list is a type to hold information about
    // variable arguments
    va_list ap;

    // va_start must be called before accessing
    // variable argument list
    va_start(ap, arg_count);

    // Now arguments can be accessed one by one
    // using va_arg macro. Initialize min as first
    // argument in list
    min = va_arg(ap, int);

    // traverse rest of the arguments to find out minimum
    for (i = 2; i <= arg_count; i++)
        if ((a = va_arg(ap, int)) < min)
            min = a;

    // va_end should be executed before the function
    // returns whenever va_start has been previously
    // used in that function
    va_end(ap);

    return min;
}

// Driver code
int main()
{
    int count = 5;
    printf("Minimum value is %d", min(count, 12, 67, 6, 7, 100));
    return 0;
}
```

这里我们使用宏来实现变量参数的功能。

*   在函数定义中使用 va_list 类型变量。

    ```cpp
    int a_function(int x, ...)
    {
        va_list a_list;
        va_start( a_list, x );
    }
    ```

*   使用 int 参数和 va_start 宏将 va_list 变量初始化为参数列表。宏 va_start 在 stdarg.h 头文件中定义。
*   使用 va_arg 宏和 va_list 变量访问参数列表中的每一项。
*   宏 va_end 清理分配给 va_list 变量的内存。

**另一个例子:**

```cpp
// C program to demonstrate working of 
// variable arguments to find average
// of multiple numbers.
#include <stdarg.h>
#include <stdio.h>

int average(int num, ...)
{
    va_list valist;

    int sum = 0, i;

    va_start(valist, num);
    for (i = 0; i < num; i++) 
        sum += va_arg(valist, int);

    va_end(valist);

    return sum / num;
}

// Driver code
int main()
{
    printf("Average of {2, 3, 4} = %d\n",
                         average(2, 3, 4));
    printf("Average of {3, 5, 10, 15} = %d\n",
                      average(3, 5, 10, 15));
    return 0;
}
```

输出:

```cpp
Average of {2, 3, 4} = 3
Average of {3, 5, 10, 15} = 10

```