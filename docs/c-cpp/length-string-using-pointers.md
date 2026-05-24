# 使用指针的字符串长度

> 原文:[https://www.geeksforgeeks.org/length-string-using-pointers/](https://www.geeksforgeeks.org/length-string-using-pointers/)

写一个程序，用指针找到字符串的长度。

示例:

```cpp
Input : given_string = "geeksforgeeks"
Output : length of the string = 13

Input : given_string = "coding"
Output : length of the string = 6

```

先决条件:[C 中的指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)

**使用的方法:**在本程序中，我们使用*运算符。*(星号)运算符表示变量值。声明时的*运算符表示这是一个指针，否则它表示指针所指向的内存位置的值。在下面的程序中，在 string_length 函数中，我们通过检查由“\0”表示的空值来检查是否到达了字符串的末尾。

```cpp
// C++ program  to find length of string
// using pointer arithmetic.
#include <iostream>
using namespace std;

// function to find the length
// of the string through pointers
int string_length(char* given_string)
{
    // variable to store the
    // length of the string
    int length = 0;
    while (*given_string != '\0') {
        length++ ;
        given_string++ ;
    }

    return length;
}

// Driver function
int main()
{
    // array to store the string
    char given_string[] = "geeksforgeeks";
    cout << string_length(given_string);
    return 0;
}
```

输出:

```cpp
13

```