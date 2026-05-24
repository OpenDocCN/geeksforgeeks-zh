# C |字符串|问题 6

> 原文:[https://www.geeksforgeeks.org/c-string-question-6/](https://www.geeksforgeeks.org/c-string-question-6/)

```cpp
#include<stdio.h>
int main()
{
    char str[] = "GeeksQuiz";
    printf("%s %s %s\n", &str[5], &5[str], str+5);
    printf("%c %c %c\n", *(str+6), str[6], 6[str]);
    return 0;
}
```

**(A)** 运行时错误
**(B)** 编译器错误
**(C)**uiz uiz
u u
T10】(D)小测验小测验
u u

**答案:****(D)**

**说明:**程序没有错误。以下所有表达式的意思都是一样的
&str[5]
&5[str]
str+5
由于编译器在访问数组元素之前会将数组操作转换为指针，因此以上所有表达式都会产生相同的地址。

同样，下面所有的表达都有同样的意思。
*(str+6)
str[6]
6[str]