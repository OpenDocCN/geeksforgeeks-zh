# 退出 C++ 中的一个循环

> 原文:[https://www.geeksforgeeks.org/exit-a-loop-in-c/](https://www.geeksforgeeks.org/exit-a-loop-in-c/)

**退出 C++ 中的一个循环:**如果省略了迭代语句([](https://www.geeksforgeeks.org/c-c-for-loop-with-examples/)**[](https://www.geeksforgeeks.org/c-c-while-loop-with-examples/)**或[](https://www.geeksforgeeks.org/c-c-do-while-loop-with-examples/)**语句)的条件，则[循环](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)不会终止，除非用户通过 [**中断**](https://www.geeksforgeeks.org/break-statement-cc/)[**继续**](https://www.geeksforgeeks.org/continue-statement-cpp/) 、[明确退出](https://www.geeksforgeeks.org/goto-statement-in-c-cpp/)******

### ****<u>一些常见的退出循环的方式如下</u>:****

****[**Break**](https://www.geeksforgeeks.org/break-statement-cc/) **:** 此语句是用于终止循环的循环控制语句。下面是 C++ 程序来说明 break 语句的使用:****

## ****c++****

```cpp
**// C++ program to illustrate the use
// of the break statement
#include <iostream>
using namespace std;

// Function to illustrate the use
// of break statement
void useOfBreak()
{
    for (int i = 0; i < 40; i++) {

        cout << "Value of i: "
             << i << endl;

        // If the value of i is
        // equal to 2 terminate
        // the loop
        if (i == 2) {
            break;
        }
    }
}

// Driver Code
int main()
{

    // Function Call
    useOfBreak();

    return 0;
}**
```

******输出:**

```cpp
Value of i: 0
Value of i: 1
Value of i: 2

```**** 

******说明:**在上面的代码中，循环在 **i** =2 之后终止，并在 2 之前打印 **i** 的值，即从 0 到 2。****

****[**Continue**](https://www.geeksforgeeks.org/continue-statement-cpp/)**:**Continue 语句用于到达循环体的末尾，而不是完全退出循环。它跳过迭代语句的其余部分。break 和 continue 的主要区别在于， **break** 语句完全终止循环，而 **continue** 语句仅终止当前迭代。****

****下面是 C++ 程序的使用说明**继续**语句:****

****T5】c++ T7

```cpp
// C++ program to illustrate the
// use of the continue statement

#include <iostream>
using namespace std;

// Function to illustrate the use
// of continue statement
void useOfContinue()
{
    for (int i = 0; i < 5; i++) {

        // If the value of i is the
        // same as 2 it will terminate
        // only the current iteration
        if (i == 2) {
            continue;
        }

        cout << "The Value of i: "
             << i << endl;
    }
}

// Driver Code
int main()
{
    // Function Call
    useOfContinue();

    return 0;
}
```

T8********T10**输出:**T1

**说明:**在上面的代码中，循环终止对 **i** =2 的迭代，并打印 2 前后的 **i** 的值。因此，它只终止给定的迭代，而不是循环。

[**【后藤】**](https://www.geeksforgeeks.org/goto-statement-in-c-cpp/) **:** 这个语句是一个无条件跳转语句，用于转移程序的控制权。它允许程序的执行流程跳转到函数中的指定位置。唯一的限制是您不能跳过初始化或进入异常处理程序。

下面是 C++ 程序来说明 **goto** 语句的使用:

## c++

```cpp
// C++ program to illustrate the use
// of goto statement
#include <iostream>
using namespace std;

// Function to illustrate the use
// of goto statement
void useOfGoto()
{
    // Local variable declaration
    int i = 1;

// Do-while loop execution
LOOP:
    do {
        if (i == 2) {

            // Skips the iteration
            i = i + 1;

            goto LOOP;
        }

        cout << "value of i: "
             << i << endl;
        i = i + 1;

    } while (i < 5);
}

// Driver Code
int main()
{
    // Function call
    useOfGoto();

    return 0;
}
```

**输出:**

```cpp
value of i: 1
value of i: 3
value of i: 4

```

**解释:**在上面的代码中，它跳转到函数内的给定位置，即 LOOP。****