# Break和Continue语句的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-break-and-continue-statement-in-c/](https://www.geeksforgeeks.org/difference-between-break-and-continue-statement-in-c/)

在本文中，我们将讨论 [C](https://www.geeksforgeeks.org/c-programming-language/) 中 `break` 和 `continue` 语句之间的区别。它们是用于改变程序流程的同一类型的语句，但是它们之间有一些区别。

[`break` 语句](https://www.geeksforgeeks.org/break-statement-cc/)：该语句终止最小的封闭循环（即 `while`、[do-while](https://www.geeksforgeeks.org/c-c-do-while-loop-with-examples/)、[for 循环](https://www.geeksforgeeks.org/range-based-loop-c/) 或 [switch 语句](https://www.geeksforgeeks.org/switch-statement-cc/)）。下面是同样的程序来说明：

## 示例：break 语句

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

**输出：**

```cpp
i = 0, j = 0 1 
i = 1, j = 0 1 
i = 2, j = 0 1 
i = 3, j = 0 1 
i = 4, j = 0 1
```

**说明：** 在上面的程序中，当变量 `j` 的值变为 `2` 时，内部 `for` 循环总是结束。

[`continue` 语句](https://www.geeksforgeeks.org/continue-statement-cpp/)：该语句跳过循环语句的剩余部分，开始循环的下一次迭代。下面是同样的程序来说明：

## 示例：continue 语句

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

**输出：**

```cpp
i = 0, j = 0 1 3 4 
i = 1, j = 0 1 3 4 
i = 2, j = 0 1 3 4 
i = 3, j = 0 1 3 4 
i = 4, j = 0 1 3 4
```

**说明：** 在上面的程序中，当变量 `j` 的值变为 `2` 时，内部 `for` 循环总是跳过迭代。

**Break和Continue语句之间的表格差异：**

| Break语句 | Continue语句 |
| --- | --- |
| Break语句用于退出循环结构。 | Continue语句不用于退出循环结构。 |
| `break`语句通常与`switch`语句一起使用，它也可以用于`while`循环、`do-while`循环或`for`循环。 | `continue`语句不与`switch`语句一起使用，但可以用于`while`循环、`do-while`循环或`for`循环。 |
| 当遇到`break`语句时，控制立即退出循环结构。 | 当遇到`continue`语句时，控制自动转移到循环语句的开始处。 |
| **语法：** `break;` | **语法：** `continue;` |