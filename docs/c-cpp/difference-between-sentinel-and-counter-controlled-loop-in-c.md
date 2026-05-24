# C

中哨兵和计数器控制回路的区别

> 原文:[https://www . geeksforgeeks . org/c 环中哨点和计数器控制环之间的差异/](https://www.geeksforgeeks.org/difference-between-sentinel-and-counter-controlled-loop-in-c/)

**哨点控制回路**

哨兵控制的循环也称为无限重复循环，因为在循环开始执行之前，迭代次数是未知的。在 sentinel 控制的循环中，一个称为 sentinel value 的特殊值用于将循环控制表达式从 true 更改为 false，以确定是否执行循环体。当我们事先不知道循环将被执行多少次时，哨兵控制循环是有用的。哨兵控制循环的一个例子是处理大小未知的文本文件中的数据。

下面是程序说明哨点控制回路在[C](https://www.geeksforgeeks.org/c/):

## C

```cpp
// The following program does the work
// of finding a length of a string using
// sentinel controlled loop
#include <stdio.h>

// Function to find the
// length of the string
void lengthOfString(char* string)
{
    int count = 0, i = 0;
    char temp;

    // Pointer to string
    temp = string[0];

    // Iterate till temp points to NULL
    while (temp != '\0') {
        count++ ;
        i++ ;
        temp = string[i];
    }

    // Print the length of the string
    printf("The length of string is %d",
           count);
}

// Driver Code
int main()
{
    // Given String
    char string[] = "GeeksForGeeks";

    // Function Call
    lengthOfString(string);
    return 0;
}
```

**输出:**

```cpp
The length of string is 13

```