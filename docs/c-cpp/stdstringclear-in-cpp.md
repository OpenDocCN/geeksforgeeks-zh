# STD::string::c++ 中的 clear

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdstringclear-in-CPP/

字符串内容被设置为空字符串，删除之前的任何内容，因此其大小为 0 个字符。
**参数:**无
**返回值:**无

```cpp
void string ::clear ()
- Removes all characters (makes string empty)
- Doesn't throw any error
- Receives no parameters and returns nothing
```

```cpp
// CPP code to illustrate
// clear() function

#include <iostream>
#include <string>
using namespace std;

// Function to demo clear()
void clearDemo(string str)
{
    // Deletes all characters in string
    str.clear();

    cout << "After clear : ";
    cout << str;
}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Before clear : ";
    cout << str << endl;
    clearDemo(str);

    return 0;
}
```

**输出:**

```cpp
Before clear : Hello World!
After clear : 

```

 **相关文章:**[STD::string::erase](https://www.geeksforgeeks.org/stdstringerase-in-c/)
本文由 **Sakshi Tiwari** 供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。