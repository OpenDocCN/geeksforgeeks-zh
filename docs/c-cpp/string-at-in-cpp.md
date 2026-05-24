# c++ 中()处的字符串

> 原文:[https://www.geeksforgeeks.org/string-at-in-cpp/](https://www.geeksforgeeks.org/string-at-in-cpp/)

**std::string::at** 可用于从给定字符串中逐个字符地提取字符。
它支持两种不同的语法，两种语法都有相似的参数:
**语法 1:**

```cpp
char& string::at (size_type idx)
```

**语法 2:**

```cpp
const char& string::at (size_type idx) const

idx : index number
Both forms return the character that has the index idx (the first character has index 0).
For all strings, an index greater than or equal to length() as value is invalid.
If the caller ensures that the index is valid, she can use operator [], which is faster.

Return value : Returns character at the specified position in the string.

Exception : Passing an invalid index (less than 0 
or greater than or equal to size()) throws an out_of_range exception.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to demonstrate std::string::at

#include <iostream>
using namespace std;

// Function to demonstrate std::string::at
void atDemo(string str)
{
    cout << str.at(5);

    // Below line throws out of
    // range exception as 16 > length()
    // cout << str.at(16);
}

// Driver code
int main()
{
    string str("GeeksForGeeks");
    atDemo(str);
    return 0;
}
```

输出:

```cpp
F
```

**应用**

**std::string::at** 可用于从字符串中提取字符。下面是同样的简单代码。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to extract characters from a given string

#include <iostream>
using namespace std;

// Function to demonstrate std::string::at
void extractChar(string str)
{
    char ch;

    // Calculating the length of string
    int l = str.length();
    for (int i = 0; i < l; i++) {
        ch = str.at(i);
        cout << ch << " ";
    }
}

// Driver code
int main()
{
    string str("GeeksForGeeks");
    extractChar(str);
    return 0;
}
```

输出:

```cpp
G e e k s F o r G e e k s 
```

本文由 **Pushpanjali Chauhan** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。