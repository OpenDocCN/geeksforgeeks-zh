# std::string::append() 在 C++ 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdstring append-in-c/

此成员函数在字符串末尾追加字符。

## Syntax 1

追加字符串 `str` 的字符。如果结果大小超过最大字符数，则抛出 `length_error`。

```cpp
string& string::append (const string& str)
```

`str` 是要追加的字符串。
返回值：`*this`。

```cpp
// CPP code to demonstrate append(str)
#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate append()
void appendDemo(string str1, string str2)
{
    // Appends str2 in str1
    str1.append(str2);
    cout << "Using append() : ";
    cout << str1 << endl;
}

// Driver code
int main()
{
    string str1("Hello World! ");
    string str2("GeeksforGeeks");

    cout << "Original String : " << str1 << endl;
    appendDemo(str1, str2);

    return 0;
}
```

输出：

```cpp
Original String : Hello World! 
Using append() : Hello World! GeeksforGeeks
```

## Syntax 2

最多追加字符串 `str` 的 `str_num` 个字符，起始索引为 `str_idx`。如果 `str_idx > str.size()` 则抛出 `out_of_range`。如果结果大小超过最大字符数，则抛出 `length_error`。

```cpp
string& string::append (const string& str, size_type str_idx, size_type str_num)
```

`str` 是要追加的字符串。
`str_num` 是字符数量。
`str_idx` 是索引号。
返回值：`*this`。

```cpp
// CPP code to demonstrate 
// append(const char* chars, size_type chars_len)
#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate append()
void appendDemo(string str1, string str2)
{
    // Appends 5 characters from 0th index of
    // str2 to str1
    str1.append(str2, 0, 5);
    cout << "Using append() : ";
    cout << str1;
}

// Driver code
int main()
{
    string str1("GeeksforGeeks ");
    string str2("Hello World! ");

    cout << "Original String : " << str1 << endl;
    appendDemo(str1, str2);

    return 0;
}
```

输出：

```cpp
Original String : GeeksforGeeks 
Using append() : GeeksforGeeks Hello
```

## Syntax 3

追加 C 风格字符串 `cstr` 的字符。如果结果大小超过最大字符数，则抛出 `length_error`。

```cpp
string& string::append (const char* cstr)
```

`*cstr` 是指向 C 风格字符串的指针。
注意：`cstr` 不能是空指针 (`NULL`)。
返回值：`*this`。

```cpp
// CPP code to demonstrate append(const char* cstr)
#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate append
void appendDemo(string str)
{
    // Appends "GeeksforGeeks"
    // in str
    str.append("GeeksforGeeks");
    cout << "Using append() : ";
    cout << str << endl;
}

// Driver code
int main()
{
    string str("World of ");

    cout << "Original String : " << str << endl;
    appendDemo(str);

    return 0;
}
```

输出：

```cpp
Original String : World of 
Using append() : World of GeeksforGeeks
```

## Syntax 4

追加字符数组 `chars` 的 `chars_len` 个字符。如果结果大小超过最大字符数，则抛出 `length_error`。

```cpp
string& string::append (const char* chars, size_type chars_len)
```

`*chars` 是指向要追加的字符数组的指针。
`chrs_len` 是从 `*chars` 中追加的字符数量。
注意：`chars` 必须至少包含 `chars_len` 个字符。
返回值：`*this`。

```cpp
// CPP code to demonstrate 
// (const char* chars, size_type chars_len)
#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate append
void appendDemo(string str)
{
    // Appends 5 characters from "GeeksforGeeks"
    // to str
    str.append("GeeksforGeeks", 5);
    cout << "Using append() : ";
    cout << str << endl;
}

// Driver code
int main()
{
    string str("World of ");

    cout << "Original String : " << str << endl;
    appendDemo(str);

    return 0;
}
```

输出：

```cpp
Original String : World of 
Using append() : World of Geeks
```

## Syntax 5

追加 `num` 个字符 `c`。如果结果大小超过最大字符数，则抛出 `length_error`。

```cpp
string& string::append (size_type num, char c)
```

`num` 是出现次数。
`c` 是要重复追加的字符。
返回值：`*this`。

```cpp
// CPP code to illustrate
// string& string::append (size_type num, char c)
#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate append
void appendDemo(string str)
{
    // Appends 10 occurrences of '$'
    // to str
    str.append(10, '$');
    cout << "After append() : ";
    cout << str;
}

// Driver code
int main()
{
    string str("#########");

    cout << "Original String : " << str << endl;
    appendDemo(str);

    return 0;
}
```

输出：

```cpp
Original String : #########
After append() : #########$$$$$
```

## Syntax 6

追加范围 `[beg, end)` 内的所有字符。如果结果大小超过最大字符数，则抛出 `length_error`。

```cpp
string& string::append (InputIterator beg, InputIterator end)
```

`first`, `last`：指向序列中初始位置和最终位置的输入迭代器。
返回值：`*this`。

```cpp
// CPP code  to illustrate
// append (InputIterator beg, InputIterator end)
#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate append
void appendDemo(string str1, string str2)
{
    // Appends all characters from
    // str2.begin()+5, str2.end() to str1
    str1.append(str2.begin() + 5, str2.end());
    cout << "Using append : ";
    cout << str1;
}

// Driver code
int main()
{
    string str1("Hello World! ");
    string str2("GeeksforGeeks");

    cout << "Original String : " << str1 << endl;
    appendDemo(str1, str2);

    return 0;
}
```

输出：

```cpp
Original String : Hello World! 
Using append : Hello World! forGeeks
```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。