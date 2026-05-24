# std::string::push_back()在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdstringpush_back-in-cpp/](https://www.geeksforgeeks.org/stdstringpush_back-in-cpp/)

提供 **push_back()** 成员函数追加字符。将字符 c 追加到字符串的末尾，使其长度增加一。
**语法:**

```cpp
void string:: push_back (char c)
Parameters:  Character which to be appended. 
Return value: None
Error: throws length_error if the 
resulting size exceeds the maximum number of characters(max_size).

```

```cpp
// CPP code for to illustrate 
// std::string::push_back()

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate push_back()
void push_backDemo(string str1, string str2)
{
    // Appends character by character str2
    // at the end of str1
    for(int i = 0; str2[i] != '\0'; i++)
    {
        str1.push_back(str2[i]);
    }
    cout << "After push_back : ";
    cout << str1;
}

// Driver code
int main()
{
    string str1("Geeksfor");
    string str2("Geeks");

    cout << "Original String : " << str1 << endl;
    push_backDemo(str1, str2);

    return 0;
}
```

输出:

```cpp
Original String : Geeksfor
After push_back : GeeksforGeeks

```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。