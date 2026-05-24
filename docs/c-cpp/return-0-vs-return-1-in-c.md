# 在 C++ 中返回 0 vs 返回 1

> 原文:[https://www.geeksforgeeks.org/return-0-vs-return-1-in-c/](https://www.geeksforgeeks.org/return-0-vs-return-1-in-c/)

**C/c++ 中的 Return 语句:**

*   [C](https://www.geeksforgeeks.org/c-programming-language/)[c++ ](https://www.geeksforgeeks.org/c-plus-plus/)支持返回语句，也叫[跳转语句](https://www.geeksforgeeks.org/return-statement-in-c-cpp-with-examples/)。
*   它用于从函数返回值或停止函数的执行。有关返回语句的更多信息，请参考文章[C/c++ 中的返回语句，并附带示例](https://www.geeksforgeeks.org/return-statement-in-c-cpp-with-examples/)。

有两种使用返回语句的情况:

**<u>方法 1。主功能</u>内部:**

*   在这种情况下，return 语句停止程序的执行， **0** 或 **1** 将表示执行状态。
*   这些状态码在 **C 语言**中只是长期作为约定使用，因为该语言不支持[对象和类](https://www.geeksforgeeks.org/c-classes-and-objects/)，以及异常。
*   **返回 0:** 返回 **0** 意味着程序将成功执行，并完成了它想要做的事情。
*   **返回 1:** 返回 **1** 表示[执行程序](https://www.geeksforgeeks.org/how-does-a-c-program-executes/)时出现了一些错误，它没有执行它想要做的事情。

**重要特征**T2【回归声明:

*   如果退出时状态不是 **0** ，则打印一条错误信息到[标准错误](https://www.geeksforgeeks.org/error-handling-c-programs/)。
*   根据[操作系统](https://www.geeksforgeeks.org/operating-systems/)关于返回代码有不同的约定。
*   如果执行了一些无效操作，操作系统本身可能会用特定的退出状态代码终止程序。

下面是一个程序来说明[主功能](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/)中**返回 0** 和**返回 1** 的用法:

## C++

```cpp
// C++ program to divide two numbers
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Given integers
    int a = 5, b = 0;

    if (b == 0) {

        // The below line is used to print
        // the message in the error window
        // fprintf(stderr, "Division by zero"
        //                 " is not possible.");

        // Print the error message
        // as return is -1
        printf("Division by zero is"
               " not possible.");
        return -1;
    }

    // Else print the division of
    // two numbers
    cout << a / b << endl;

    return 0;
}
```

**Output:**

```cpp
Division by zero is not possible.

```

**<u>方法二。在自定义功能</u>里面:**

*   C++ 将[布尔型](https://www.geeksforgeeks.org/bool-data-type-in-c/)视为完全独立的数据类型，只有两个不同的值，即**真**和**假**。
*   值 1 和 0 属于 int 类型，不能隐式转换为布尔值，这意味着:
    *   **<u>返回 0:</u>** 从函数返回 false。
    *   **<u>返回 1:</u>** 从一个函数返回真。

下面是一个程序来说明用户自定义功能中**返回 0** 和**返回 1** 的用法:

## C++

```cpp
// C++ program to demonstrate the use
// of return 0 and return 1 inside
// user-defined function
#include <iostream>
using namespace std;

// Utility function returning 1 or
// 0 based on given age
int checkAdultUtil(int age)
{
    if (age >= 18)
        return 1;
    else
        return 0;
}

// Function to check for age
void checkAdult(int age)
{
    // Checking on the basis
    // of given age
    if (checkAdultUtil(age))
        cout << "You are an adult\n";
    else
        cout << "You are not an adult\n";
}

// Driver Code
int main()
{
    // Given age
    int age = 25;

    // Function Call
    checkAdult(age);

    return 0;
}
```

**Output:**

```cpp
You are an adult

```

**结论:**

<figure class="table">

| **Use case** | **returns 0** | **returns 1** |
| In the main function | 0 indicates that the program was successfully executed. | Returning 1 in the main function indicates that the program was not successfully executed and there were some errors. |
| In the custom function | 0 in indicates that the custom function is returning false. | 1 indicates that the custom function is returning true. |

</figure>