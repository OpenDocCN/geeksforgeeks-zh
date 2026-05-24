# C 小测验–102 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-102-question-5/](https://www.geeksforgeeks.org/c-c-quiz-102-question-5/)

在以下程序片段的上下文中，选择最佳答案。

```cpp
#include "stdio.h"
int arr[10][10][10];
int main()
{
 arr[5][5][5] = 123;
 return 0;
}
```

给定的 printf 语句中的哪一个能够打印 arr[5][5][5]

```cpp
(i) printf("%d",arr[5][5][5]);
(ii) printf("%d",*(*(*(arr+5)+5)+5));
(iii) printf("%d",(*(*(arr+5)+5))[5]);
(iv) printf("%d",*((*(arr+5))[5]+5));
```

**(A)** 只有(I)会编译并打印 123。
**【B】**㈠和㈡都会编译，都会打印 123。
**【C】**只有(I)、(ii)和(iii)会编译，但只有(I)和(ii)会打印 123。
**【D】**只有(I)、(ii)和(iii)会编译，三者都会打印 123。
**【E】**所有(I)、(ii)、(iii)和(iv)将编译，但只有(I)和(ii)将打印 123。
所有(I)、(ii)、(iii)和(iv)将编译，所有将打印 123。

**回答:**

**说明:**对于数组，我们可以将数组下标运算符[]转换为指针顺从运算符*并有适当的偏移量。意思是 arr[x]等于*(arr+x)。基本上，这两个是可以互换的。同样的概念也可以应用于多维数组。

这就是为什么上面的 4 个 printf 都指的是同一个元素，即*arr【5】【5】【5】【5】*

[本题竞猜](https://www.geeksforgeeks.org/c-quiz-102-gq/)