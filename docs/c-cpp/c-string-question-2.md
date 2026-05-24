# C |字符串|问题 2

> 原文:[https://www.geeksforgeeks.org/c-string-question-2/](https://www.geeksforgeeks.org/c-string-question-2/)

以下程序的输出是什么？

```cpp
# include <stdio.h>

int main()
{
   char str1[] = "GeeksQuiz";
   char str2[] = {'G', 'e', 'e', 'k', 's', 'Q', 'u', 'i', 'z'};
   int n1 = sizeof(str1)/sizeof(str1[0]);
   int n2 = sizeof(str2)/sizeof(str2[0]);
   printf("n1 = %d, n2 = %d", n1, n2);
   return 0;
}
```

**(A)** n1 = 10，n2 = 9

**(B)** n1 = 10，n2 = 10

**(C)** n1 = 9，n2 = 9

**(D)** n1 = 9，n2 = 10

**回答:** **(A)**

**说明:**str 1 的大小是 10，str2 的大小是 9。

当用双引号中的字符串初始化数组时，编译器会在末尾添加一个“\0”。