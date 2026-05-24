# 什么是 C++ 中的数组衰减？如何预防？

> 原文:[https://www . geeksforgeeks . org/什么是阵列衰减-in-c-如何防止/](https://www.geeksforgeeks.org/what-is-array-decay-in-c-how-can-it-be-prevented/)

**什么是阵衰？**
一个数组的类型和维度的丢失被称为数组的衰减。这通常发生在我们通过值或指针将数组传递给函数的时候。它所做的是，它发送第一个地址到数组，这是一个指针，因此数组的大小不是原来的，而是被内存中的指针占用的。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate array decay
#include<iostream>
using namespace std;

// Driver function to show Array decay
// Passing array by value
void aDecay(int *p)
{
    // Printing size of pointer
    cout << "Modified size of array is by "
            " passing by value: ";
    cout << sizeof(p) << endl;
}

// Function to show that array decay happens 
// even if we use pointer
void pDecay(int (*p)[7])
{
    // Printing size of array
    cout << "Modified size of array by "
            "passing by pointer: ";
    cout << sizeof(p) << endl;
}

int main()
{
    int a[7] = {1, 2, 3, 4, 5, 6, 7,};

    // Printing original size of array
    cout << "Actual size of array is: ";
    cout << sizeof(a) <<endl;

    // Passing a pointer to array
    aDecay(a);

    // Calling function by pointer
    pDecay(&a);   

    return 0;
}
```

输出:

```cpp
Actual size of array is: 28
Modified size of array by passing by value: 8
Modified size of array by passing by pointer: 8
```

在上面的代码中，实际数组有 7 个 int 元素，因此有 28 个大小。但是通过值和指针的调用，数组衰减为指针并打印 1 个指针的大小，即 8(32 位中的 4 个)。
**如何防止阵衰？**
处理衰减的典型解决方案是将数组的大小也作为参数传递，而不在数组参数上使用 size of(详见[本](https://www.geeksforgeeks.org/using-sizof-operator-with-array-paratmeters/))
防止数组衰减的另一种方法是通过引用将数组发送到函数中。这可以防止数组转换成指针，从而防止衰减。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate prevention of
// decay of array
#include<iostream>
using namespace std;

// A function that prevents Array decay
// by passing array by reference
void fun(int (&p)[7])
{
    // Printing size of array
    cout << "Modified size of array by "
            "passing by reference: ";
    cout << sizeof(p) << endl;
}

int main()
{
    int a[7] = {1, 2, 3, 4, 5, 6, 7,};

    // Printing original size of array
    cout << "Actual size of array is: ";
    cout << sizeof(a) <<endl;

    // Calling function by reference
    fun(a);

    return 0;
}
```

输出:

```cpp
Actual size of array is: 28
Modified size of array by passing by reference: 28
```

在上面的代码中，通过引用传递数组解决了数组的衰减问题。两种情况下的尺寸都是 28。
本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。