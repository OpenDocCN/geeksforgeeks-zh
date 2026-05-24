# 用实例说明 C 中的记忆集()

> 原文:[https://www.geeksforgeeks.org/memset-c-example/](https://www.geeksforgeeks.org/memset-c-example/)

***memset()*** 用于用特定值填充内存块。
memset()函数的语法如下:

```cpp
// ptr ==> Starting address of memory to be filled
// x   ==> Value to be filled
// n   ==> Number of bytes to be filled starting 
//         from ptr to be filled
void *memset(void *ptr, int x, size_t n);

```

请注意，ptr 是一个[空指针](https://www.geeksforgeeks.org/void-pointer-c-cpp/)，这样我们就可以将任何类型的指针传递给这个函数。

让我们在 C 语言中看到一个简单的例子来演示 memset()函数是如何使用的:

```cpp
// C program to demonstrate working of memset()
#include <stdio.h>
#include <string.h>

int main()
{
    char str[50] = "GeeksForGeeks is for programming geeks.";
    printf("\nBefore memset(): %s\n", str);

    // Fill 8 characters starting from str[13] with '.'
    memset(str + 13, '.', 8*sizeof(char));

    printf("After memset():  %s", str);
    return 0;
}
```

输出:

```cpp
Before memset(): GeeksForGeeks is for programming geeks.
After memset(): GeeksForGeeks........programming geeks.

```

**解释:** (str + 13)指向字符串“GeeksForGeeks 是给编程极客的”的第一个空格(基于 0 的索引)，memset()设置字符“.”从字符串的第一个' '开始，直到给定字符串的 8 个字符位置，因此我们得到如上所示的输出。

```cpp
// C program to demonstrate working of memset()
#include <stdio.h>
#include <string.h>

void printArray(int arr[], int n)
{
   for (int i=0; i<n; i++)
      printf("%d ", arr[i]);
}

int main()
{
    int n = 10;
    int arr[n];

    // Fill whole array with 0.
    memset(arr, 0, n*sizeof(arr[0]));
    printf("Array after memset()\n");
    printArray(arr, n);

    return 0;
}
```

输出:

```cpp
0 0 0 0 0 0 0 0 0 0
```

 **练习:**
预测下面程序的输出。

```cpp
// C program to demonstrate working of memset()
#include <stdio.h>
#include <string.h>

void printArray(int arr[], int n)
{
   for (int i=0; i<n; i++)
      printf("%d ", arr[i]);
}

int main()
{
    int n = 10;
    int arr[n];

    // Fill whole array with 100.
    memset(arr, 10, n*sizeof(arr[0]));
    printf("Array after memset()\n");
    printArray(arr, n);

    return 0;
}
```

请注意，上面的代码没有将数组值设置为 10，因为 memset 是逐个字符工作的，并且一个整数包含多个字节(或字符)。

然而，如果我们用-1 替换 10，我们会得到-1 值。因为-1 的表示在 char 和 int 的情况下都包含全 1。

**参考:**T2【memset 手册页(linux)

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。