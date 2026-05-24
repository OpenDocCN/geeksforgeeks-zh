# C |数组|问题 2

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-2/](https://www.geeksforgeeks.org/c-arrays-question-2/)

预测以下程序的输出:

```cpp
#include <stdio.h>

int main()
{
    int arr[5];
    // Assume base address of arr is 2000 and size of integer is 32 bit
    printf("%u %u", arr + 1, &arr + 1);

return 0;
} 
```

- (A) 2004 2020
- (B) 2004 2004
- (C) 2004 垃圾值
- (D) 由于 Address-of 运算符不能与数组名一起使用，程序无法编译

答案: (A)

## 解释

在这个地址上加 1 得到地址加上数组的类型的大小。在数组名称前应用的地址操作符给出整个数组的地址。在这个地址上加 1 得到地址加上整个数组的大小。