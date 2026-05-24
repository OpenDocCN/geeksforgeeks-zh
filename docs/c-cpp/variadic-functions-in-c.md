# C 中的变量函数

> 原文:[https://www.geeksforgeeks.org/variadic-functions-in-c/](https://www.geeksforgeeks.org/variadic-functions-in-c/)

[变量函数](https://www.geeksforgeeks.org/variadic-function-templates-c/)是[函数](https://www.geeksforgeeks.org/functions-in-c/)，可以接受可变数量的[参数](https://www.geeksforgeeks.org/command-line-arguments-in-c-cpp/)。在 [C 编程](https://www.geeksforgeeks.org/c/)中，变量函数增加了程序的灵活性。它需要一个固定的参数，然后可以传递任意数量的参数。变量函数由至少一个固定变量和最后一个参数省略号(…)组成。

**语法:**

```cpp
int function_name(data_type variable_name, ...);
```

传递的参数值可以通过名为[的头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)访问:

```cpp
#include <stdarg.h>
```

[< stdarg.h >](https://www.geeksforgeeks.org/header-files-in-c-c-with-examples/) 包括以下方法:

<figure class="table">

| **方法** | **描述** |
| va_start(va_list ap，argN) | 这允许访问变量函数参数。 |
| va_arg(va_list ap，类型) | 这个访问下一个变量函数参数。 |
| va_copy（va_list dest， va_list src） | 这就复制了变量函数的参数。 |
| va_end（va_list ap） | 这结束了变量函数参数的遍历。 |

</figure>

这里 **va_list** 保存 **va_start** 、 **va_arg** 、 **va_end** 、 **va_copy** 需要的信息。

**程序 1:**

以下简单的 [C 程序](https://www.geeksforgeeks.org/c/)将演示变量函数 **AddNumbers()** 的工作原理:

## C

```cpp
// C program for the above approach

#include <stdarg.h>
#include <stdio.h>

// Variadic function to add numbers
int AddNumbers(int n, ...)
{
    int Sum = 0;

    // Declaring pointer to the
    // argument list
    va_list ptr;

    // Initializing argument to the
    // list pointer
    va_start(ptr, n);

    for (int i = 0; i < n; i++)

        // Accessing current variable
        // and pointing to next one
        Sum += va_arg(ptr, int);

    // Ending argument list traversal
    va_end(ptr);

    return Sum;
}

// Driver Code
int main()
{
    printf("\n\n Variadic functions: \n");

    // Variable number of arguments
    printf("\n 1 + 2 = %d ",
           AddNumbers(2, 1, 2));

    printf("\n 3 + 4 + 5 = %d ",
           AddNumbers(3, 3, 4, 5));

    printf("\n 6 + 7 + 8 + 9 = %d ",
           AddNumbers(4, 6, 7, 8, 9));

    printf("\n");

    return 0;
}
```

**Output:** 

```cpp
Variadic functions: 

 1 + 2 = 3 
 3 + 4 + 5 = 12 
 6 + 7 + 8 + 9 = 30
```

**程序 2:** 下面是由变量函数**组成的 C 程序**:

## C

```cpp
// C program for the above approach
#include <stdarg.h>
#include <stdio.h>

// Variadic function to add numbers
int LargestNumber(int n, ...)
{
    int min = 0;

    // Declaring pointer to the
    // argument list
    va_list ptr;

    // Initializing argument to the
    // list pointer
    va_start(ptr, n);

    for (int i = 0; i < n; i++) {

        // Accessing current variable
        // and pointing to next
        int temp = va_arg(ptr, int);
        min = temp > min ? temp : min;
    }

    // End of argument list traversal
    va_end(ptr);

    return min;
}

// Driver Code
int main()
{
    printf("\n\n Variadic functions: \n");

    // Variable number of arguments
    printf("\n %d ",
           LargestNumber(2, 1, 2));

    printf("\n %d ",
           LargestNumber(3, 3, 4, 5));

    printf("\n %d ",
           LargestNumber(4, 6, 7, 8, 9));

    printf("\n");

    return 0;
}
```

**Output:** 

```cpp
Variadic functions: 

 2 
 5 
 9
```