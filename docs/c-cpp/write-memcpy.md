# 自己写 memcpy()和 memmove()

> 原文:[https://www.geeksforgeeks.org/write-memcpy/](https://www.geeksforgeeks.org/write-memcpy/)

[memcpy](http://geeksquiz.com/memcpy-in-cc/) 功能用于将一个数据块从源地址复制到目的地址。下面是它的原型。

```cpp
void * memcpy(void * destination, const void * source, size_t num);
```

其思想是简单地将给定的地址类型转换为 char *(char 需要 1 个字节)。然后一个接一个地将数据从源复制到目标。下面是这个想法的实现。

```cpp
// A C implementation of memcpy()
#include<stdio.h>
#include<string.h>

void myMemCpy(void *dest, void *src, size_t n)
{
   // Typecast src and dest addresses to (char *)
   char *csrc = (char *)src;
   char *cdest = (char *)dest;

   // Copy contents of src[] to dest[]
   for (int i=0; i<n; i++)
       cdest[i] = csrc[i];
}

// Driver program
int main()
{
   char csrc[] = "GeeksforGeeks";
   char cdest[100];
   myMemCpy(cdest, csrc, strlen(csrc)+1);
   printf("Copied string is %s", cdest);

   int isrc[] = {10, 20, 30, 40, 50};
   int n = sizeof(isrc)/sizeof(isrc[0]);
   int idest[n], i;
   myMemCpy(idest, isrc,  sizeof(isrc));
   printf("\nCopied array is ");
   for (i=0; i<n; i++)
     printf("%d ", idest[i]);
   return 0;
}
```

输出:

```cpp
Copied string is GeeksforGeeks
Copied array is 10 20 30 40 50
```

## **什么是 [memmove()](http://geeksquiz.com/memmove-in-cc/) ？**

memmove()与 memcpy()类似，因为它也将数据从源复制到目标。当源地址和目的地址重叠时，memcpy()会导致问题，因为 memcpy()只是将数据从一个位置逐个复制到另一个位置。例如，考虑下面的程序。

```cpp
// Sample program to show that memcpy() can lose data.
#include <stdio.h>
#include <string.h>
int main()
{
   char csrc[100] = "Geeksfor";
   memcpy(csrc+5, csrc, strlen(csrc)+1);
   printf("%s", csrc);
   return 0;
}
```

输出:

```cpp
GeeksGeeksfor
```

由于输入地址重叠，上述程序会覆盖原始字符串并导致数据丢失。

```cpp
// Sample program to show that memmove() is better than memcpy()
// when addresses overlap.
#include <stdio.h>
#include <string.h>
int main()
{
   char csrc[100] = "Geeksfor";
   memmove(csrc+5, csrc, strlen(csrc)+1);
   printf("%s", csrc);
   return 0;
}
```

输出:

```cpp
GeeksGeeksfor
```

## **如何实现 memmove()？**

这里的技巧是使用临时数组，而不是直接从 src 复制到 dest。临时数组的使用对于处理源地址和目的地址重叠的情况非常重要。

```cpp
//C++ program to demonstrate implementation of memmove()
#include<stdio.h>
#include<string.h>

// A function to copy block of 'n' bytes from source
// address 'src' to destination address 'dest'.
void myMemMove(void *dest, void *src, size_t n)
{
   // Typecast src and dest addresses to (char *)
   char *csrc = (char *)src;
   char *cdest = (char *)dest;

   // Create a temporary array to hold data of src
   char *temp = new char[n];

   // Copy data from csrc[] to temp[]
   for (int i=0; i<n; i++)
       temp[i] = csrc[i];

   // Copy data from temp[] to cdest[]
   for (int i=0; i<n; i++)
       cdest[i] = temp[i];

   delete [] temp;
}

// Driver program
int main()
{
   char csrc[100] = "Geeksfor";
   myMemMove(csrc+5, csrc, strlen(csrc)+1);
   printf("%s", csrc);
   return 0;
}
```

输出:

```cpp
GeeksGeeksfor
```

**优化:**
算法效率低下(如果使用临时数组，时间确实会翻倍)。除非真的不可能，否则应避免双份。

在这种情况下，虽然很容易通过选择复制方向来避免重复复制。事实上，这就是 memmove()库函数的作用。

通过比较 src 和 dst 地址，您应该能够发现它们是否重叠。

–如果它们不重叠，您可以在任何方向上复制
–如果它们重叠，找到目标的哪一端与源重叠，并相应地选择复制方向。
–如果目的地的开头重叠，从头到尾复制
–如果目的地的结尾重叠，从头到尾复制
–另一个优化是按字长复制。只是要小心处理边界条件。
-进一步的优化是对副本使用向量指令，因为它们是连续的。

本文由 Saurabh Jain 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。