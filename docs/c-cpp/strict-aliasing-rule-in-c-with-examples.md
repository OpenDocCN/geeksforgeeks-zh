# C 中的严格混叠规则，示例

> 原文:[https://www . geesforgeks . org/strict-aliasing-rule-in-c-with-examples/](https://www.geeksforgeeks.org/strict-aliasing-rule-in-c-with-examples/)

**混叠:**混叠是指可以使用不同的名称访问同一个内存位置的情况。

**例如**如果一个函数取了两个值相同的指针 **A** 和 **B** ，那么名称**A【0】**就化名为**B【0】**，也就是说我们说的指针 **A** 和 **B** 相互别名。

下面是程序说明**走样**中 C:

## C

```cpp
// C program to illustrate aliasing
#include <stdio.h>

// Function to add 10 to b
int gfg(int* a, int* b)
{
    *b = *b + 10;
    return *a;
}

// Driver Code
int main()
{
    // Given data
    int data = 20;

    // Function Call with aliasing
    int result = gfg(&data, &data);

    // Print the data
    printf("%d ", result);
}
```

T10】输出:

```cpp
30

```