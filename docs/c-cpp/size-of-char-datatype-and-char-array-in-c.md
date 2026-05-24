# C 中字符数据类型和字符数组的大小

> 原文:[https://www . geesforgeks . org/char-size-datatype-and-char-array-in-c/](https://www.geeksforgeeks.org/size-of-char-datatype-and-char-array-in-c/)

给定一个 char 变量和一个 char 数组，任务是编写一个程序，用 c 语言找到这个 char 变量和 char 数组的大小。

**示例:**

```cpp
Input: ch = 'G', arr[] = {'G', 'F', 'G'}
Output: 
Size of char datatype is: 1 byte
Size of char array is: 3 byte

Input: ch = 'G', arr[] = {'G', 'F'}
Output: 
Size of char datatype is: 1 byte
Size of char array is: 2 byte

```

**方法:**
在下面的程序中，要找到 char 变量和 char 数组的大小:

*   首先，charType 中定义了 char 变量，arr 中定义了 char 数组。
*   然后，使用 [sizeof()运算符](https://www.geeksforgeeks.org/sizeof-operator-c/)计算字符变量的大小。
*   然后将整个数组的大小除以第一个变量的大小，就可以得到 char 数组的大小。

下面是查找 char 变量和 char 数组大小的 C 程序:

```cpp
// C program to find the size of
// char data type and char array

#include <stdio.h>

int main()
{

    char charType = 'G';
    char arr[] = { 'G', 'F', 'G' };

    // Calculate and Print
    // the size of charType
    printf("Size of char datatype is: %ld byte\n",
           sizeof(charType));

    // Calculate the size of char array
    size_t size = sizeof(arr) / sizeof(arr[0]);

    // Print the size of char array
    printf("Size of char array is: %ld byte",
           size);

    return 0;
}
```

**Output:**

```cpp
Size of char datatype is: 1 byte
Size of char array is: 3 byte

```