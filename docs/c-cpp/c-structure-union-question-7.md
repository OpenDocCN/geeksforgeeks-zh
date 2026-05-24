# C |结构&联合|问题 7

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-7/](https://www.geeksforgeeks.org/c-structure-union-question-7/)

```cpp
union test
{
    int x;
    char arr[8];
    int y;
};

int main()
{
    printf("%d", sizeof(union test));
    return 0;
}
```

预测上述程序的输出。假设一个整数的大小是 4 字节，字符的大小是 1 字节。还假设不需要对齐。
**(A)**12
**(B)**16
**(C)**8
**(D)**编译器错误

**答案:****(C)**

**解释:**当我们声明一个并集时，为该类型的并集变量分配的内存等于它的最大成员所需的内存，并且在上面的例子中，“char arr[8]”是最大的成员。因此联合测试的大小是 8 字节。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)