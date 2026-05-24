# C |指针基础|问题 6

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-6/](https://www.geeksforgeeks.org/c-pointers-question-6/)

```cpp
#include<stdio.h>
int main()
{
    int arr[] = {10, 20, 30, 40, 50, 60};
    int *ptr1 = arr;
    int *ptr2 = arr + 5;
    printf("Number of elements between two pointer are: %d.", 
                                (ptr2 - ptr1));
    printf("Number of bytes between two pointers are: %d",  
                              (char*)ptr2 - (char*) ptr1);
    return 0;
}
```

假设一个 int 变量取 4 字节，一个 char 变量取 1 字节
**(A)** 两个指针之间的元素个数为:5。
两个指针之间的字节数为:20
**(B)** 两个指针之间的元素数为:20。
两个指针之间的字节数为:20
**(C)** 两个指针之间的元素数为:5。
两个指针之间的字节数为:5
**(D)** 编译器错误
**(E)** 运行时错误

**答案:****(A)**

**解释:**数组名给出数组中第一个元素的地址。所以当我们做“* ptr1 = arr，ptr1 开始保存元素 10 的地址。“arr + 5”给出了第 6 个元素的地址，因为算术是使用指针完成的。所以“ptr2-ptr1”给出 5。当我们执行'(char *)ptr2 '时，ptr2 被类型转换为 char 指针，并且字符的大小是一个字节，指针算法在考虑字符指针时发生。所以我们得到 5*sizeof(int)/sizeof(char)作为两个指针的差。