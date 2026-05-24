# C |数组|问题 11

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-11/](https://www.geeksforgeeks.org/c-arrays-question-11/)

C 执行数组越界检查吗？以下程序的输出是什么？

```cpp
int main()
{
    int i;
    int arr[5] = {0};
    for (i = 0; i <= 5; i++)
        printf("%d ", arr[i]);
    return 0;
}
```

**(A)** 编译器错误:数组索引越界。
**(B)** 总是打印 0 五次，然后是垃圾值
**(C)** 程序总是崩溃。
**(D)** 程序可能会打印 5 次 0，然后是垃圾值，或者如果地址(arr+5)无效，程序可能会崩溃。

**回答:****(D)**

**说明:**

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)