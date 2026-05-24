# 仅使用一个循环打印图案|设置 1(使用设置)

> 原文:[https://www . geesforgeks . org/print-pattern-only-use-one-loop/](https://www.geeksforgeeks.org/print-pattern-using-only-one-loop/)

使用循环下的单行代码打印如下所示的简单模式。

**例:** 

```cpp
Input : 5
Output :
    *
   **
  ***
 ****
*****

Input : 6
Output :
     *
    **
   ***
  ****
 *****
******

```

**设置 w(n)** 创建 n 列，并从右侧填充这 n 列。我们用一个给定的字符填充其中的 I，这里我们[使用字符串构造器](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)创建一个带有 I 星号的字符串。

**setfill()** 用于设置流中的填充字符。这里我们用它在 n 列中用空格(或' ')填充剩余的 n-i-1 个位置。

```cpp
// CPP program to print a pattern  using only
// one loop.  <iomanip> is header file for stfill()
// and setw()
#include<iostream>
#include<iomanip>
using namespace std;

void generatePattern(int n)
{
    // Iterate for n lines
    for (int i=1 ; i<=n ; i++)
        cout << setfill(' ') << setw(n)
             << string(i, '*') << endl;

    // Remove multi-line commenting characters below
    // to get PATTERN WITH CHARACTERS IN LEFT AND 
    // SPACE IN RIGHT
    /* for (int i=1 ; i<=n ; i++)
        cout << left << setfill(' ')
             << setw(n) << string(i,'*') << endl; */
}

// Driver code
int main()
{
    int n = 6;
    generatePattern(n);
    return 0;
}
```

输出:

```cpp
     *
    **
   ***
  ****
 *****
******

```

请参考下面的帖子，了解更多方法。
[仅使用一个循环打印图案|设置 2(使用继续)](https://www.geeksforgeeks.org/print-pattern-using-one-loop-continue-statement/)

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。