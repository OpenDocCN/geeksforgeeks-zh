# 在C中不使用字符串函数和循环打印子串

> 原文: [https://www.geeksforgeeks.org/print-substring-of-a-given-string-without-using-any-string-function-and-loop-in-c/](https://www.geeksforgeeks.org/print-substring-of-a-given-string-without-using-any-string-function-and-loop-in-c/)

用C写一个函数`mysubstr()`，不使用任何字符串函数，不使用任何循环，打印字符串的子字符串。*函数不应修改字符串的内容，也不应使用临时字符数组或字符串*。

例如`mysubstr(“geeksforgeeks”，1，3)`应该打印“*eek*”，即索引1和3之间的子字符串。

## 递归方法

一种解决方法是使用递归。感谢Gopi和oggy提出这个解决方案。

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

## 指针算术方法

**如果递归也不允许怎么办？**
我们总是可以用指针算术来改变开头部分。例如`(str + i)`给出了第i个字符的地址。为了限制结尾，我们可以在`printf`中使用宽度说明符，当*在格式字符串中使用时，该说明符可以作为参数传递*。

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

本文由**拉胡尔·贾恩**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。