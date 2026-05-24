# 在 C++ 中使用关系运算符比较字符串对象

> 原文:[https://www . geesforgeks . org/comparising-string-objects-use-relational-operators-c/](https://www.geeksforgeeks.org/comparing-string-objects-using-relational-operators-c/)

如果使用**关系运算符**比较字符串，则根据当前字符特征，它们的字符在字典上被**比较**，这意味着它从第一个字符开始逐字符比较，直到两个字符串中的字符相等或遇到空字符。

*   **Parameter:** Two strings to be compared. On the left, one is the string being compared, and on the right, the other is the string to be compared.
*   **Return type:** Relational operators return true or false values, that is, they return Boolean values, which are true if the corresponding comparison is true, otherwise they are false.

**关系运算符列表:**

*   **>** : greater than
*   **<** : less than
*   [T0】 = 【T1]: equal to
*   **！ =** : Not equal to
*   **> =** : greater than or equal to
*   **< =** : less than or equal to

**重要条件:**

1.  **s1 < s2:** A string s1 is smaller than s2 string. If so, the length of s1 is shorter than s2 or the first unmatched character is smaller.
2.  **s1 > s2:** A string s1 is larger than s2\. If one of the strings s1 is longer than s2 or the first unmatched character is larger.
3.  **<** = and **>** = have almost the same implementation and have equal additional features.
4.  If two strings are found to be the same after comparison in dictionary order, they are said to be equal.
5.  If any point from 1 to 3 is followed, then the strings are considered unequal.

```cpp
// CPP code to implement relational 
// operators on String objects
#include<iostream>
using namespace std;

void relational_operation(string s1, string s2)
{
    string s3 = s1 + s2;

    if(s1 != s2)
        cout << s1 << " is not equal to " << s2 << endl;

    if(s1 > s2)
        cout << s1 << " is greater than " << s2 << endl;

    else if(s1 < s2)
        cout << s1 << " is smaller than " << s2 << endl;

    if(s3 == s1 + s2)
        cout << s3 << " is equal to " << s1 + s2 << endl;

}

// Main function
int main()
{
    string s1("Geeks");
    string s2("forGeeks");
    relational_operation(s1, s2);

  return 0; 
}
```

输出:

```cpp
Geeks is not equal to forGeeks
Geeks is smaller than forGeeks
GeeksforGeeks is equal to GeeksforGeeks

```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。