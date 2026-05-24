# 在 C++ 中从字符串中提取所有整数

> 原文:[https://www.geeksforgeeks.org/extract-integers-string-c/](https://www.geeksforgeeks.org/extract-integers-string-c/)

给定一个字符串，从中提取所有整数单词。

示例:

```cpp
Input : str = "geeksforgeeks 12 23 practice"
Output : 12 13

Input : str = "1: Prakhar Agrawal, 2: Manish Kumar Rai, 3: Rishabh Gupta"
Output : 1 2 3

Input : str = "Ankit sleeps at 4 am."
Output : 4

```

想法是使用 **stringstream:** ，这个类的对象使用包含一系列字符的字符串缓冲区。

**算法**

```cpp
 1\. Enter the whole string into stringstream.
 2\. Extract the all words from string using loop.
 2\. Check whether a word is integer or not.

```

```cpp
/* Extract all integers from string */
#include <iostream>
#include <sstream>
using namespace std;

void extractIntegerWords(string str)
{
    stringstream ss;    

    /* Storing the whole string into string stream */
    ss << str;

    /* Running loop till the end of the stream */
    string temp;
    int found;
    while (!ss.eof()) {

        /* extracting word by word from stream */
        ss >> temp;

        /* Checking the given word is integer or not */
        if (stringstream(temp) >> found)
            cout << found << " ";

        /* To save from space at the end of string */
        temp = "";
    }
}

// Driver code
int main()
{
    string str = "1: 2 3 4 prakhar";
    extractIntegerWords(str);
    return 0;
}
```

输出:

```cpp

1 2 3 4 

```

**相关文章:**

*   [Convert strings to numbers in C++ and vice versa](https://www.geeksforgeeks.org/converting-string-to-number-and-vice-versa-in-c/)
*   [慕容留弦流〔t1〕](https://www.geeksforgeeks.org/program-extract-words-given-string/)

从给定字符串中提取单词

本文由 **[普拉哈尔·阿格沃尔](http://prakhar.info)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。