# 如何在 C 语言中通过值传递数组？

> 原文:[https://www.geeksforgeeks.org/pass-array-value-c/](https://www.geeksforgeeks.org/pass-array-value-c/)

在 C 语言中，数组名代表地址，当我们传递一个数组时，我们实际上传递的是地址，参数接收函数总是接受它们作为指针(即使我们使用[]，详见[这个](https://www.geeksforgeeks.org/why-c-treats-array-parameters-as-pointers/))。

**如何按值传递数组，即当我们传递给函数时，如何确保我们有一个数组的新副本？**
这可以通过将数组包装在一个结构中，并创建该结构类型的变量，然后为该数组赋值来实现。之后，将变量传递给其他函数，并根据需求进行修改。注意[数组成员作为参数传递时会被复制，但动态数组不是](https://www.geeksforgeeks.org/are-array-members-deeply-copied/)。因此，该解决方案仅适用于非动态数组(创建时没有 new 或 malloc)。

让我们看一个用 C 程序演示上述事实的例子:

```cpp
// C program to demonstrate passing an array
// by value using structures.
#include<stdio.h>
#include<stdlib.h>

# define SIZE 5

// A wrapper for array to make sure that array
// is passed by value.
struct ArrayWrapper
{
    int arr[SIZE];
};

// An array is passed by value wrapped in temp
void modify(struct ArrayWrapper temp)
{
    int *ptr = temp.arr;
    int i;

    // Display array contents
    printf("In 'modify()', before modification\n");
    for (i = 0; i < SIZE; ++ i)
        printf("%d ", ptr[i]);

    printf("\n");

    // Modify the array
    for (i = 0; i < SIZE; ++ i)
        ptr[i] = 100; // OR *(ptr + i)

    printf("\nIn 'modify()', after modification\n");
    for (i = 0; i < SIZE; ++ i)
        printf("%d ", ptr[i]); // OR *(ptr + i)
}

// Driver code
int main()
{
    int i;
    struct ArrayWrapper obj;
    for (i=0; i<SIZE; i++)
        obj.arr[i] = 10;

    modify(obj);

    // Display array contents
    printf("\n\nIn 'Main', after calling modify() \n");
    for (i = 0; i < SIZE; ++ i)
        printf("%d ", obj.arr[i]); // Not changed

    printf("\n");

    return 0;
}
```

输出:

```cpp
In 'modify()', before modification
10 10 10 10 10 

In 'modify()', after modification
100 100 100 100 100 

In 'Main', after calling modify() 
10 10 10 10 10 

```

 **Reference:**[http://stackoverflow.com/questions/11158858/c-pass-array-by-value](http://stackoverflow.com/questions/11158858/c-pass-array-by-value)

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。