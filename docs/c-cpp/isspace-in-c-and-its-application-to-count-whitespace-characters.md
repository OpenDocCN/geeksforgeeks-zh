# C/c++ 中的 isspace()及其对空白字符计数的应用

> 原文:[https://www . geeksforgeeks . org/is space-in-c-and-it-application-to-count-空格-字符/](https://www.geeksforgeeks.org/isspace-in-c-and-its-application-to-count-whitespace-characters/)

**ISS space()函数**
在 C++ 中，ISS space 是用于字符串和字符处理的预定义函数，cstring 是字符串函数所需的头文件，cctype 是字符函数所需的头文件。

该函数用于检查参数是否包含任何空白字符。
c++ 中有很多类型的空白字符，比如-

*   “–空间
*   \ '–水平选项卡
*   \ n '–换行符
*   \ v '–垂直标签
*   \ f '–提要
*   \ r '–回车

```cpp
Syntax :
int isspace(int x)
x : x is character to be checked

```

**应用程序**
给定一个字符串，我们需要使用 isspace()函数计算字符串中的空白字符数。

示例:

```cpp
Input : string = 'Geeks for geeks'
Output : 2

Input :string = 'My name is Ayush'
Output : 3

```

```cpp
// C program to illustrate
// isspace() function
#include <ctype.h>
#include <stdio.h>
int main()
{
    // taking input
    char ch = ' ';

    // checking is it space?
    if (isspace(ch))
        printf("\nEntered character is space");
    else
        printf("\nEntered character is not space");
}
```

输出:

```cpp
Entered character is space

```

 isspace()函数用于查找给定句子中的空格数。
**例:**

```cpp
Input : This is a good website
Output : Number of spaces in the sentence is : 4

Input : heyy this is geeksforgeeks
Output : Number of spaces in the sentence is : 3

Input : hello how can I help you
Output : Number of spaces in the sentence is : 5
```

**算法**
1。逐个字符遍历给定的字符串直到其长度，检查字符是否为空白字符。
2。如果它是一个空白字符，将计数器加 1，否则遍历到下一个字符。
3。打印计数器的值。

```cpp
// C program to illustrate
// isspace() function
#include <ctype.h>
#include <stdio.h>

// Function for counting spaces
int cnt_space(int i, int count, char ch)
{

    // input sentence
    char buf[50] = "Geeks for Geeks";
    ch = buf[0];

    // counting spaces
    while (ch != '\0') {
        ch = buf[i];
        if (isspace(ch))
            count++ ;

        i++ ;
    }

    // returning number of spaces
    return (count);
}
int main()
{

    char ch;
    int i = 0, count = 0;

    // Calling function
    count = cnt_space(i, count, ch);

    // printing number of spaces
    printf("\nNumber of spaces in the sentence is : %d", count);

    return 0;
}
```

输出:

```cpp
Number of spaces in the sentence is : 2
```

```cpp
// CPP program to count white spaces in a string
#include <iostream>
#include <cstring>
#include <cctype>
using namespace std;

// function to calculate whitespaces
void space(string& str)
{
    int count = 0;
    int length = str.length();
    for (int i = 0; i < length; i++) {
        int c = str[i];
        if (isspace(c))
            count++ ;
    }
    cout << count;
}

// Driver Code
int main()
{
    string str = "Geeks for geeks";
    space(str);
    return 0;
}
```

输出:

```cpp
2

```

本文由**Ayush Saxena****Kanchan Ray**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。