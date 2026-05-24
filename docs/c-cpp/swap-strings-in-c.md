# 交换字符串的 C 功能

> 原文:[https://www.geeksforgeeks.org/swap-strings-in-c/](https://www.geeksforgeeks.org/swap-strings-in-c/)

让我们考虑下面的程序。

```cpp
#include<stdio.h>
void swap(char *str1, char *str2)
{
  char *temp = str1;
  str1 = str2;
  str2 = temp;
}  

int main()
{
  char *str1 = "geeks";
  char *str2 = "forgeeks";
  swap(str1, str2);
  printf("str1 is %s, str2 is %s", str1, str2);
  getchar();
  return 0;
}
```

程序的输出是 *str1 是极客，str2 是伪造者*。所以上面的 swap()函数不交换字符串。该函数只改变局部指针变量，这些改变不会反映在函数外部。

让我们看看交换字符串的正确方法:

**方法 1(交换指针)**
如果你是[使用字符串的字符指针](https://www.geeksforgeeks.org/storage-for-strings-in-c/)(不是数组)，那么改变 str1 和 str2 来指向彼此的数据。即交换指针。在一个函数中，如果我们想要改变一个指针(显然我们想要改变反映在函数之外)，那么我们需要传递一个指针给指针。

```cpp
#include<stdio.h>

/* Swaps strings by swapping pointers */ 
void swap1(char **str1_ptr, char **str2_ptr)
{
  char *temp = *str1_ptr;
  *str1_ptr = *str2_ptr;
  *str2_ptr = temp;
}  

int main()
{
  char *str1 = "geeks";
  char *str2 = "forgeeks";
  swap1(&str1, &str2);
  printf("str1 is %s, str2 is %s", str1, str2);
  getchar();
  return 0;
}
```

如果使用字符数组存储字符串，则不能应用此方法。

**方法 2(交换数据)**
如果你是[使用字符数组存储字符串](https://www.geeksforgeeks.org/storage-for-strings-in-c/)那么首选的方式是交换两个数组的数据。

```cpp
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

/* Swaps strings by swapping data*/
void swap2(char *str1, char *str2)
{
  char *temp = (char *)malloc((strlen(str1) + 1) * sizeof(char));
  strcpy(temp, str1);
  strcpy(str1, str2);
  strcpy(str2, temp);
  free(temp);
}  

int main()
{
  char str1[10] = "geeks";
  char str2[10] = "forgeeks";
  swap2(str1, str2);
  printf("str1 is %s, str2 is %s", str1, str2);
  getchar();
  return 0;
}
```

此方法不能应用于存储在只读内存块中的字符串。

如果你在上面的文章中发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。