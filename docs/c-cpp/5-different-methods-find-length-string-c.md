# 5 种在 C++ 中求字符串长度的不同方法

> 原文:[https://www . geesforgeks . org/5-不同方法-查找-长度-字符串-c/](https://www.geeksforgeeks.org/5-different-methods-find-length-string-c/)

字符串是字符序列或字符数组。使用字符数组的字符串声明和定义类似于任何其他数据类型数组的声明和定义。

**要点:**

1.  [The constructor of the string class](https://www.geeksforgeeks.org/stdstring-class-in-c/) will set it as a C-style string ending in' \0'.
2.  The size () function is consistent with other STL containers (such as vectors, maps, etc.). ) and length () conform to most people's intuitive concepts of strings, such as words, sentences or paragraphs. We say that the length of a paragraph is not its size, so length () is to make things easier to read.

**方法查找字符串的长度**

1.  **Use the string:: size:** method string:: size to return the length of the string in bytes.
2.  **Use the string:: length:** method String:: length to return the length of the string in bytes. String::size and string::length are synonyms and return exactly the same value.
3.  **Use the C library function strlen () method:** The C library function size_t strlen(const char *str) calculates the maximum length of the string, but does not include the terminated null characters.
4.  **Using while loop:** Using the traditional method, initialize the counter equal to 0, and increment the counter from the beginning of the string to the end of the string (terminate the null character).
5.  **Use the for loop:** Initialize the counter equal to 0, and increment the counter from the beginning of the string to the end of the string (ending the null character).

**示例:**

```cpp
Input: "Geeksforgeeks"
Output: 13

Input: "Geeksforgeeks\0 345"
Output: 13

Input: "Geeksforgeeks \0 345"
Output: 14

```

```
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

    // 1\. size of string object using size() method
    cout << str.size() << endl;

    // 2\. size of string object using length method
    cout << str.length() << endl;

    // 3\. size using old style
    // size of string object using strlen function
    cout << strlen(str.c_str()) << endl;

    // The constructor of string will set it to the
    // C-style string,
    // which ends at the '\0'

    // 4\. size of string object Using while loop
    // while 'NOT NULL'
    int i = 0;
    while (str[i])
        i++ ;
    cout << i << endl;

    // 5\. size of string object using for loop
    // for(; NOT NULL 😉
    for (i = 0; str[i]; i++)
        ;
    cout << i << endl;

    return 0;
}
```cpp

**Output:**

```
13
13
13
13
13

```

本文由 [**普拉哈尔·阿格沃尔**](http://prakhar.info) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。