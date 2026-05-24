# 当输入中有空行时，如何在 C++ 中使用 getline()？

> 原文:[https://www . geeksforgeeks . org/如何使用-c 中的 get line-in-当输入中有黑线时/](https://www.geeksforgeeks.org/how-to-use-getline-in-c-when-there-are-black-lines-in-input/)

在 C++ 中，如果我们需要从一个流中读取几个句子，通常首选的方法是使用 getline()函数。它可以读取，直到遇到换行符或看到用户提供的分隔符。

下面是一个 c++ 中的示例程序，它读取四个句子，并在最后

```cpp
// A simple C++ program to show working of getline
#include <iostream>
#include <cstring>
using namespace std;
int main()
{
    string str;
    int t = 4;
    while (t--)
    {
        // Read a line from standard input in str
        getline(cin, str);
        cout << str << " : newline" << endl;
    }
    return 0;
}
```

用“:newline”显示它们

**样本输入:**

```cpp
 This
 is
 Geeks
 for
```

**如预期输出为:**

```cpp
This : newline
is  : newline
Geeks : newline
for : newline
```

以上输入输出看起来不错，输入中间有空行可能会有问题。

**样本输入:**

```cpp
This

is 

Geeks

for
```

**输出:**

```cpp
This : newline
 : newline
is  : newline
 : newline
```

它不会打印最后两行。原因是 getline()一直读取，直到遇到 enter，即使没有读取任何字符。因此，即使第三行没有任何内容，getline()也会将其视为一行。进一步观察第二行的问题。

可以修改代码以排除此类空行。

修改代码:

```cpp
// A simple C++ program that uses getline to read
// input with blank lines
#include <iostream>
#include <cstring>
using namespace std;
int main()
{
    string str;
    int t = 4;
    while (t--)
    {
        getline(cin, str);

        // Keep reading a new line while there is
        // a blank line
        while (str.length()==0 )
            getline(cin, str);

        cout << str << " : newline" << endl;
    }
    return 0;
}
```

输入:

```cpp
This

is 

Geeks

for
```

输出:

```cpp
This : newline
is  : newline
Geeks : newline
for : newline
```

本文由**沙林南大**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。