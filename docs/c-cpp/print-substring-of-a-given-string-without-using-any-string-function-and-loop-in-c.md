# 打印给定字符串的子串，不使用任何字符串函数，在 C

中循环

> 原文:[https://www . geesforgeks . org/print-substring-of-a-给定字符串-不使用任何字符串函数和循环 in-c/](https://www.geeksforgeeks.org/print-substring-of-a-given-string-without-using-any-string-function-and-loop-in-c/)

用 C 写一个函数 mysubstr()，不使用任何字符串函数，不使用任何循环，打印字符串的子字符串。*函数不应修改字符串的内容，也不应使用临时字符数组或字符串*。

例如*my substr(“geeksforgeeks”，1，3)* 应该打印“ *eek* ”，即索引 1 和 3 之间的子字符串。

一种解决方法是使用递归。感谢 Gopi 和 oggy 提出这个解决方案。

```cpp
#include<stdio.h>

// This function prints substring of str[] between low and
// high indexes (both inclusive).  
void mysubstr(char str[], int low, int high)
{
    if (low<=high)
    {
        printf("%c", str[low]);
        mysubstr(str, low+1, high);
    }
}

int main ()
{
    char str[] = "geeksforgeeks";
    mysubstr(str, 1, 3);
    return 0;
}
```

输出:

```cpp
eek
```

**如果递归也不允许怎么办？**
我们总是可以用指针算术来改变开头部分。例如(str + i)给出了第 I 个字符的地址。为了限制结尾，我们可以在 printf 中使用宽度说明符，当*在格式字符串中使用时，该说明符可以作为参数传递。

```cpp
#include <stdio.h>

// This function prints substring of str[] between low and
// high indexes (both inclusive).  
void mysubstr(char str[], int low, int high)
{
    printf("%.*s", high-low+1, (str+low));
}

int main ()
{
    char str[] = "geeksforgeeks";
    mysubstr(str, 1, 3);
    return 0;
}
```

输出:

```cpp
eek
```

本文由**拉胡尔·贾恩**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论