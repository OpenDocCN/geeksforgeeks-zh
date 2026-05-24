# C++ 中 switch 语句大小写标签的数据类型？

> 原文：[https://www.geeksforgeeks.org/data-type-of-case-labels-of-switch-statement-in-c/](https://www.geeksforgeeks.org/data-type-of-case-labels-of-switch-statement-in-c/)

在 C++ `switch` 语句中，每个 `case` 标签的表达式必须是整数常量表达式。
比如下面的程序编译失败。

## 示例：使用非常量导致编译失败

```cpp
/* Using non-const in case label */
#include<stdio.h>
int main()
{
  int i = 10;
  int c = 10;
  switch(c)
  {
    case i: // not a "const int" expression
         printf("Value of c = %d", c);
         break;
    /*Some more cases */
  }
  return 0;
}
```

将 `i` 声明为 `const` 可以使上述程序工作。

## 示例：使用常量正常工作

```cpp
#include<stdio.h>
int main()
{
  const int i = 10;
  int c = 10;
  switch(c)
  {
    case i:  // Works fine
         printf("Value of c = %d", c);
         break;
    /*Some more cases */
  }
  return 0;
}
```

注：以上事实仅针对 C++。在 C 语言中，两个程序都会产生一个错误。在 C 语言中，使用整数常量不会导致错误。

**程序使用 `switch` 寻找两个数字之间最大的数字：**

## C 语言示例

```cpp
#include<stdio.h>
int main()
{
  int n1=10,n2=11;

  // n1 > n2 (10 > 11) is false so using
  // logical operator '>', n1 > n2 produces 0
  // (0 means false, 1 means true) So, case 0
  // is executed as 10 > 11 is false. Here we
  // have used type cast to convert boolean to int,
  // to avoid warning.

  switch((int)(n1 > n2))
  {
    case 0:
         printf("%d is the largest\n", n2);
         break;
    default:
         printf("%d is the largest\n", n1);
  }

  // n1 < n2 (10 < 11) is true so using logical
  // operator '<', n1 < n2 produces 1 (1 means true,
  // 0 means false) So, default is executed as we
  // don't have case 1 to be executed.

  switch((int)(n1 < n2))
  {
    case 0:
         printf("%d is the largest\n", n1);
         break;
    default:
         printf("%d is the largest\n", n2);
  }

  return 0;
}
//This code is contributed by Santanu
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。