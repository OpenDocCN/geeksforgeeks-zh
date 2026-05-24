# std::string::resize() 在 C++ 中

> 噻: [https://www.geeksforgeeks.org/stdstringresize-in-c/](https://www.geeksforgeeks.org/stdstringresize-in-c/)

`resize()` 用于更改字符数。下面我们将描述 C++ 中 `std::string::resize()` 支持的两种语法。
**返回值:** 无。

## 语法 1

将字符串的字符数调整为 `num`。

```cpp
void string::resize(size_type num)
```

- `num`: 新字符串长度，以字符数表示。
- **错误:**
    - 如果 `num` 等于 `string::npos`，则抛出 `length_error`。
    - 如果结果大小超过最大字符数 (`max_size()`)，则抛出 `length_error`。

**注意:** 如果 `num > size()`，那么剩余的字符用 `'\0'` 初始化。

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

**输出:**

```cpp
Original String : GeeksforGeeks 
Using resize : Geeks
```

## 语法 2

使用一个字符来填充 `size()` 和 `num` 之间的差异。

```cpp
void string::resize(size_type num, char c)
```

- `num`: 新字符串长度，以字符数表示。
- `c`: 用于填充新字符空间的字符。
    - 如果 `num > size()`：使用字符 `c` 填充空间。
    - 如果 `num < size()`：字符串被简单地调整为 `num` 个字符的大小。
- **错误:**
    - 如果 `num` 等于 `string::npos`，则抛出 `length_error`。
    - 如果结果大小超过最大字符数 (`max_size()`)，则抛出 `length_error`。

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
    // 15 and fill the space with '$'
    str.resize(15, '$');
    cout << str << endl;
    cout << "If num < size() : ";

    // Resizes str to a string with
    // 5 initial characters only
    str.resize(5, '$');
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

**输出:**

```cpp
Original String : GeeksforGeeks
Using resize :
If num > size() : GeeksforGeeks$$$
If num < size() : Geeks
```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者将文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。