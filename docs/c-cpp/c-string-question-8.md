# C |字符串|问题 8

> 原文:[https://www.geeksforgeeks.org/c-string-question-8/](https://www.geeksforgeeks.org/c-string-question-8/)

输出？

```cpp
int main()
{
    char a[2][3][3] = {'g','e','e','k','s','q','u','i','z'};
    printf("%s ", **a);
    return 0;
}
```

**(A)** 编译器错误
**(B)** 极客 squiz 后跟垃圾字符
**(C)** 极客 squiz
**(D)** 运行时错误

**答案:****(C)**

**解释:**我们已经创建了一个应该有 2*3*3 (= 18)个元素的 3D 数组，但我们正在初始化在 C 语言中，当我们初始化一个数组中较少的元素时，如果是 char，所有未初始化的元素都变成' \0 '，如果是整数，所有未初始化的元素都变成' 0 '。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)