# C |数组|问题 9

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-9/](https://www.geeksforgeeks.org/c-arrays-question-9/)

预测以下程序的输出:

```cpp
#include <stdio.h>
#define SIZE(arr) sizeof(arr) / sizeof(*arr);
void fun(int* arr, int n)
{
    int i;
    *arr += *(arr + n - 1) += 10;
}

void printArr(int* arr, int n)
{
    int i;
    for(i = 0; i < n; ++ i)
        printf("%d ", arr[i]);
}

int main()
{
    int arr[] = {10, 20, 30};
    int size = SIZE(arr);
    fun(arr, size);
    printArr(arr, size);
    return 0;
}
```

**(A)**20 30 40
**(B)**20 20 40
**(C)**50 20 40
**(D)**编译时错误

**答案:****(C)**

**解释:**问题的关键在于表述: **arr*复合运算符(此处 *+=* )具有从右到左的关联性。第一个 10 被添加到数组的最后一个元素。然后将结果添加到数组的第一个元素中。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)