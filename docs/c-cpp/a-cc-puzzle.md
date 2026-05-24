# 一个 C/C++ 函数调用谜题

> 原文:[https://www.geeksforgeeks.org/a-cc-puzzle/](https://www.geeksforgeeks.org/a-cc-puzzle/)

考虑以下程序。用 C 和 C++ 编译器编译时，预测它的输出。

## C

```cpp
void func()
{
    /* definition */
}

int main()
{
    func();
    func(2);
}
```

上面的程序在 C 中编译很好，但是在 C++ 中不编译。

在 C++ 中，func()等价于 func(void)
在 C 中，func()等价于 func(…)

更多用 C 而不是 C++ 编译的程序参考[这个](https://www.geeksforgeeks.org/difference-int-main-int-mainvoid/)和[这个](https://www.geeksforgeeks.org/write-c-program-wont-compiler-c/)。

本文由**拉胡尔·米塔尔**整理。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。