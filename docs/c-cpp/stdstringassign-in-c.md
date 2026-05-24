# std::string::assign()在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdstringassign-in-c/](https://www.geeksforgeeks.org/stdstringassign-in-c/)

成员函数 **assign()** 用于赋值，它为字符串赋值一个新值，替换其当前内容。
**语法 1:** 赋值字符串 str。

```cpp
string& string::assign (const string& str)

str :  is the string to be assigned.
Returns : *this

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for assign (const string& str)
#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate assign
void assignDemo(string str1, string str2)
{
    // Assigns str2 to str1
    str1.assign(str2);
    cout << "After assign() : ";
    cout << str1;

}

// Driver code
int main()
{
    string str1("Hello World!");
    string str2("GeeksforGeeks");

    cout << "Original String : " << str1 << endl;
    assignDemo(str1, str2);

    return 0;
}
```

**输出:**

```cpp
Original String : Hello World!
After assign() : GeeksforGeeks

```

**语法 2:** 从索引 str_idx 开始最多分配字符串的 str_num 个字符。如果 str_idx > str，则抛出范围外。大小()。

```cpp
string& string::assign (const string& str, size_type str_idx, size_type str_num)

str : is the string to be assigned.
str_idx : is the index number in str.
str_num : is the number of characters picked 
from str_idx to assign
Return : *this

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// assign(const string& str, size_type
// str_idx, size_type str_num)

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate assign
void assignDemo(string str1, string str2)
{
    // Assigns 8 characters from
    // 5th index of str2 to str1
    str1.assign(str2, 5, 8);
    cout << "After assign() : ";
    cout << str1;

}

// Driver code
int main()
{
    string str1("Hello World!");
    string str2("GeeksforGeeks");

    cout << "Original String : " << str1 << endl;
    assignDemo(str1, str2);

    return 0;
}
```

**输出:**

```cpp
Original String : Hello World!
After assign() : forGeeks

```

**语法 3:** 指定 C 字符串 cstr 的字符。如果结果大小超过最大字符数，它将引发 length_error。

```cpp
string & string::assign (const char* cstr)

Assigns all characters of cstr up to but not including '\0'.
Returns : *this.
Note : that cstr may not be a null pointer (NULL).

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for assign (const char* cstr)

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate assign
void assignDemo(string str)
{
    // Assigns GeeksforGeeks to str
    str.assign("GeeksforGeeks");
    cout << "After assign() : ";
    cout << str;

}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Original String : " << str << endl;
    assignDemo(str);

    return 0;
}
```

**输出:**

```cpp
Original String : Hello World!
After assign() : GeeksforGeeks

```

**语法 4:** 分配字符数组字符的 chars_len 字符。如果结果大小超过最大字符数，它将引发 length_error。

```cpp
string& string::assign (const char* chars, size_type chars_len)

*chars : is the pointer to the array to be assigned.
chars_len : is the number of characters to be assigned from 
character array.
Note : that chars must have at least chars_len characters.
Returns : *this.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// string& string::assign
// (const char* chars, size_type chars_len)

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate assign
void assignDemo(string str)
{
    // Assigns first 5 characters of
    // GeeksforGeeks to str
    str.assign("GeeksforGeeks", 5);
    cout << "After assign() : ";
    cout << str;

}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Original String : " << str << endl;
    assignDemo(str);

    return 0;
}
```

**输出:**

```cpp
Original String : Hello World!
After assign() : Geeks

```

**语法 5:** 指定字符 c 出现的次数。如果次数等于字符串::NPO，将引发 length_error

```cpp
string & string::assign (size_type num, char c)

num :  is the number of occurrences to be assigned.
c :  is the character which is to be assigned repeatedly. 
Throws length_error if the resulting size exceeds the maximum number(max_size) of characters.
Returns : *this.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for string&
// string::assign (size_type num, char c)

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate assign
void assignDemo(string str)
{
    // Assigns 10 occurrences of 'x'
    // to str
    str.assign(10, 'x');
    cout << "After assign() : ";
    cout << str;

}

// Driver code
int main()
{
    string str("#########");

    cout << "Original String : " << str << endl;
    assignDemo(str);

    return 0;
}
```

**输出:**

```cpp
Original String : #########
After assign() : xxxxxxxxxx

```

**语法 6:** 分配范围内的所有字符[beg，end。如果范围超出字符串的实际内容，它将抛出**长度错误**。

```cpp
template <class InputIterator>
   string& assign (InputIterator first, InputIterator last)
first, last : Input iterators to the initial and final positions 
in a sequence.

Returns : *this.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for string&
// string::assign (size_type num, char c)

#include <iostream>
#include <string>
using namespace std;

// Function to demonstrate assign
void assignDemo(string str)
{
    string str1;

    // Assigns all characters between
    // str.begin()+6 and str.end()-0 to str1
    str1.assign(str.begin()+6, str.end()-0);
    cout << "After assign() : ";
    cout << str1;

}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Original String : " << str << endl;
    assignDemo(str);

    return 0;
}
```

**输出:**

```cpp
Original String : Hello World!
After assign() : World!

```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。