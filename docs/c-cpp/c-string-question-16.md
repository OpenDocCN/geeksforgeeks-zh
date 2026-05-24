# C |字符串|问题 16

> 原文:[https://www.geeksforgeeks.org/c-string-question-16/](https://www.geeksforgeeks.org/c-string-question-16/)

以下 C 程序的输出？假设包含了所有必要的头文件

```cpp
int main()
{
    char *s1 = (char *)malloc(50);
    char *s2 = (char *)malloc(50);
    strcpy(s1, "Geeks");
    strcpy(s2, "Quiz");
    strcat(s1, s2);
    printf("%s", s1);
    return 0;
}
```

**(A)** 极客 sQuiz
**(B)** 极客
**(C)** 极客小测验
**(D)** 小测验

**答案:****(A)**

**说明:** strcpy 把\0 放在最后。

strcat 从\0 开始，连接字符串并将\0 放在末尾。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/string-gq/)