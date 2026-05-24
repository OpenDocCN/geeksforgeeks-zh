# C

中中断和继续语句的区别

> 原文:[https://www . geesforgeks . org/break-and-continue-statement-in-c/](https://www.geeksforgeeks.org/difference-between-break-and-continue-statement-in-c/)

在本文中，我们将讨论 [C](https://www.geeksforgeeks.org/c-programming-language/) 中**中断**和**继续**语句之间的区别。它们是用于改变程序流程的同一类型的语句，但是它们之间有一些区别。

[**<u>break 语句</u>**](https://www.geeksforgeeks.org/break-statement-cc/) **:** 该语句终止最小的封闭循环(即 **while** 、 [do-while](https://www.geeksforgeeks.org/c-c-do-while-loop-with-examples/) 、 [for 循环](https://www.geeksforgeeks.org/range-based-loop-c/)或 [switch 语句](https://www.geeksforgeeks.org/switch-statement-cc/))。下面是同样的程序来说明:

## C

```cpp
// C program to illustrate the
// break statement
#include <stdio.h>

// Driver Code
int main()
{

    int i = 0, j = 0;

    // Iterate a loop over the
    // range [0, 5]
    for (int i = 0; i < 5; i++) {

        printf("i = %d, j = ", i);

        // Iterate a loop over the
        // range [0, 5]
        for (int j = 0; j < 5; j++) {

            // Break Statement
            if (j == 2)
                break;

            printf("%d ", j);
        }

        printf("\n");
    }

    return 0;
}
```

**Output:**

```cpp
i = 0, j = 0 1 
i = 1, j = 0 1 
i = 2, j = 0 1 
i = 3, j = 0 1 
i = 4, j = 0 1

```

**说明:**在上面的程序中，当变量 **j** 的值变为 **2** 时，内部 for 循环总是结束。

[**<u>continue 语句</u>**](https://www.geeksforgeeks.org/continue-statement-cpp/) **:** 该语句跳过循环语句的剩余部分，开始循环的下一次迭代。下面是同样的程序来说明:

## C

```cpp
// C program to illustrate the
// continue statement
#include <stdio.h>

// Driver Code
int main()
{

    int i = 0, j = 0;

    // Iterate a loop over the
    // range [0, 5]
    for (int i = 0; i < 5; i++) {

        printf("i = %d, j = ", i);

        // Iterate a loop over the
        // range [0, 5]
        for (int j = 0; j < 5; j++) {

            // Continue Statement
            if (j == 2)
                continue;

            printf("%d ", j);
        }

        printf("\n");
    }

    return 0;
}
```

**Output:**

```cpp
i = 0, j = 0 1 3 4 
i = 1, j = 0 1 3 4 
i = 2, j = 0 1 3 4 
i = 3, j = 0 1 3 4 
i = 4, j = 0 1 3 4

```

**说明:**在上面的程序中，当变量 **j** 的值变为 **2** 时，内部 for 循环总是跳过迭代。

**<u>中断和继续语句之间的表格差异</u> :**

<figure class="table">

| Interrupt statement | Continue statement |
| --- | --- |
| Interrupt statement is used to exit loop construction. | Continue statement is not used to exit loop construction. |
| The break statement is usually used with the switch statement, and it can also be used in a while loop, a do-while loop for- a for-loop | The continue statement is not used with the switch statement, but can be used in a while loop, a do-while loop or a for-loop |
| When the break statement is encountered, the control immediately exits the loop construction. | When a continue statement is encountered, control is automatically transferred from the beginning of the loop statement. |
| **Syntax:**
Break; | **Syntax:**
Continue; |

</figure>