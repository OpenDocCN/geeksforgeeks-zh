# C |数组|问题 10

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-10/](https://www.geeksforgeeks.org/c-arrays-question-10/)

预测后续程序的输出

```cpp
int main()
{
    int i;
    int arr[5] = {1};
    for (i = 0; i < 5; i++)
        printf("%d ", arr[i]);
    return 0;
}
```

**(A)** 1 后跟四个垃圾值
**(B)**1 0 0 0 0
**(C)**1 1 1 1
1**(D)**0 0 0 0 0

**答案:****(B)**

**解释:**在 C/C++ 中，如果我们初始化一个成员较少的数组，那么所有

例如，下面的语句使用值 0 初始化大小为 1000 的数组。

```cpp
     int arr[1000] = {0};  
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)