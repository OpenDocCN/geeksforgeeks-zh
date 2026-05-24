# 5 种在 C++ 中求字符串长度的不同方法

> 原文：[https://www.geeksforgeeks.org/5-different-methods-find-length-string-c/](https://www.geeksforgeeks.org/5-different-methods-find-length-string-c/)

字符串是字符序列或字符数组。使用字符数组的字符串声明和定义类似于任何其他数据类型数组的声明和定义。

## 要点

1.  [`string`类的构造函数](https://www.geeksforgeeks.org/stdstring-class-in-c/)会将其设置为以`'\0'`结尾的C风格字符串。
2.  `size()`函数与其他STL容器（如`vector`、`map`等）保持一致，而`length()`符合大多数人对字符串（如单词、句子或段落）的直观概念。我们说一个段落的长度不是它的大小，所以`length()`是为了让事情更容易阅读。

## 查找字符串长度的方法

### 1. 使用 `string::size`
调用`string::size`方法返回字符串的字节长度。

### 2. 使用 `string::length`
调用`string::length`方法返回字符串的字节长度。`string::size`和`string::length`是同义词，返回的值完全相同。

### 3. 使用C库函数 `strlen()`
C库函数`size_t strlen(const char *str)`计算字符串的最大长度，但不包括终止的空字符。

### 4. 使用 `while` 循环
使用传统方法，初始化计数器等于0，并从字符串开头（终止空字符）递增计数器直到字符串末尾。

### 5. 使用 `for` 循环
初始化计数器等于0，并从字符串开头（终止空字符）递增计数器直到字符串末尾。

## 示例

```cpp
Input: "Geeksforgeeks"
Output: 13

Input: "Geeksforgeeks\0 345"
Output: 13

Input: "Geeksforgeeks \0 345"
Output: 14
```

```cpp
// CPP program to illustrate
// Different methods to find length
// of a string
#include <iostream>
#include <string.h>
using namespace std;
int main()
{
    // String obj
    string str = "GeeksforGeeks";

    // 1. size of string object using size() method
    cout << str.size() << endl;

    // 2. size of string object using length method
    cout << str.length() << endl;

    // 3. size using old style
    // size of string object using strlen function
    cout << strlen(str.c_str()) << endl;

    // The constructor of string will set it to the
    // C-style string,
    // which ends at the '\0'

    // 4. size of string object Using while loop
    // while 'NOT NULL'
    int i = 0;
    while (str[i])
        i++ ;
    cout << i << endl;

    // 5. size of string object using for loop
    // for(; NOT NULL 😉
    for (i = 0; str[i]; i++)
        ;
    cout << i << endl;

    return 0;
}
```

**输出：**

```
13
13
13
13
13
```

本文由 [**Prakhar Agarwal**](http://prakhar.info) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。