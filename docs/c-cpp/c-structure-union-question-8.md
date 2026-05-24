# C |结构&联合|问题 8

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-8/](https://www.geeksforgeeks.org/c-structure-union-question-8/)

```cpp
union test
{
    int x;
    char arr[4];
    int y;
};

int main()
{
    union test t;
    t.x = 0;
    t.arr[1] = 'G';
    printf("%s", t.arr);
    return 0;
}
```

预测上述程序的输出。假设一个整数的大小是 4 字节，字符的大小是 1 字节。还假设不需要对齐。
**(A)** 无打印
**(B)** G
**(C)** 垃圾字符后跟‘G’
**(D)**垃圾字符后跟‘G’，后跟更多垃圾字符
**(E)** 编译器错误

**答案:****(A)**

**解释:…o 是' \0 '的 ASCII 值。当我们做“t.arr[1] = 'G '”时，arr[]就变成了“\0G\0\0”。当我们使用“%s”打印字符串时，printf 函数从第一个字符开始，一直打印到找到一个\0。因为第一个字符本身是\0，所以不打印任何内容。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/structure-union-gq/)**