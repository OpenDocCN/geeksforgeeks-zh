# std::string::resize()在 C++ 中

> 噻:[https://www . geeksforgeeks . org/stdstringresize-in-c/](https://www.geeksforgeeks.org/stdstringresize-in-c/)

**resize()** 用于更改字符数。下面我们将描述 C++ 中 std::string::resize()支持的两种语法
**返回值:**无

**语法 1:** 将*的字符数调整为 num。

```cpp
void string ::resize (size_type num)
num: New string length, expressed in number of characters.
Errors: 
Throws length_error if num is equal to string ::npos.
Throws length_error if the resulting size exceeds the maximum number of
characters(max_size()).

```

**注意:**如果 num > size()那么，剩下的字符用' \0 '初始化。

```cpp
// CPP code for resize (size_type num)

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate insert
void resizeDemo(string str)
{

    // Resizes str to a string with
    // 5 initial characters only 
    str.resize(5);
    cout << "Using resize : ";
    cout << str;
}

// Driver code
int main()
{
    string str("GeeksforGeeks ");

    cout << "Original String : " << str << endl;
    resizeDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks 
Using resize : Geeks

```

**语法 2:** 使用一个字符来填充 size()和 num 之间的差异。

```cpp
void string ::resize (size_type num, char c )
num: is the new string length, expressed in number of characters.
c: is the character needed to fill the new character space.
If num > size() : character c is used to fill space.
If num < size() : String is simply resized to num number of characters.
Errors: 
Throws length_error if num is equal to string ::npos.
Throws length_error if the resulting size exceeds the maximum number of
characters(max_size()).

```

```cpp
// CPP code for resize (size_type num, char c )

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate insert
void resizeDemo(string str)
{
    cout << "Using resize :" << endl;
    cout << "If num > size() : ";

    // Resizes str to character length of
    // 15 and fill the space with '{content}apos;
    str.resize(15, '{content}apos;);
    cout << str << endl;
    cout << "If num < size() : ";

    // Resizes str to a string with
    // 5 initial characters only 
    str.resize(5, '{content}apos;);
    cout << str;
}

// Driver code
int main()
{
    string str("GeeksforGeeks");

    cout << "Original String : " << str << endl;
    resizeDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks
Using resize :
If num > size() : GeeksforGeeks$
If num < size() : Geeks

```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。