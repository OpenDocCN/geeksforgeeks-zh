# STD::string::find _ last _ not _ of 在 C++ 中

> 原文:[https://www . geesforgeks . org/stdstringfind _ last _ not _ of-in-CPP/](https://www.geeksforgeeks.org/stdstringfind_last_not_of-in-cpp/)

它从字符串末尾开始搜索字符串中与参数中指定的任何字符都不匹配的第一个字符。
**返回值:**成功时第一个不匹配字符的索引，如果没有找到这样的字符，则返回字符串::NPO。
**语法 1:** 搜索不是字符串元素的最后一个字符。

```cpp
size_type string::find_last_not_of (const string& str) const
str : Another string with the set of characters
to be used in the search.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for find_last_not_of (const string& str) const

#include <iostream>
using namespace std;

// Function to demonstrate find_last_not_of
void find_last_not_ofDemo(string str1, string str2)
{
    // Finds last character in str1 which
    // is not present in str2
    string::size_type ch = str1.find_last_not_of(str2);
    cout << "First unmatched character : ";
    cout << str1[ch];
}

// Driver code
int main()
{
    string str1("Hello World!");
    string str2("GeeksforGeeks");

    cout << "Original String : " << str1 << endl;
    cout << "String to be looked in : " << str2 << endl;
    find_last_not_ofDemo(str1, str2);

    return 0;
}
```

输出:

```cpp
Original String : Hello World!
String to be looked in : GeeksforGeeks
First unmatched character : !
```

**语法 2:** 从索引 idx 中搜索不是字符串元素的最后一个字符。

```cpp
size_type string::find_last_not_of (const string& str, size_type idx) const
str : Another string with the set of characters
to be used in the search.
idx : is the index number from where we have to
start finding first unmatched character.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for string::find_last_not_of
// (const string& str, size_type idx) const

#include <iostream>
using namespace std;

// Function to demonstrate find_last_not_of
void find_last_not_ofDemo(string str1, string str2)
{
    // Finds last character in str1 from index 3 which
    // is not present in str2
    string::size_type ch = str1.find_last_not_of(str2, 3);
    cout << "First unmatched character : ";
    cout << str1[ch];
}

// Driver code
int main()
{
    string str1("geeKsforgeeks");
    string str2("GeeksforGeeks");

    cout << "Original String : " << str1 << endl;
    cout << "String to be looked in : " << str2 << endl;
    find_last_not_ofDemo(str1, str2);

    return 0;
}
```

输出:

```cpp
Original String : geeKsforgeeks
String to be looked in : GeeksforGeeks
First unmatched character : K
```

**语法 3:** 搜索最后一个字符，该字符是否也是 C 字符串 cstr 的元素。

```cpp
size_type string::find_last_not_of (const char* cstr) const
cstr : Another C-string with the set of characters
to be used in the search.
```

**注意【cstr 不能是空指针(空)。** 

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for string::find_last_not_of (const char* cstr) const

#include <iostream>
using namespace std;

// Function to demonstrate find_last_not_of
void find_last_not_ofDemo(string str)
{
    // Finds last character in str which
    // is not present in "geeksforgeeks"
    string::size_type ch = str.find_last_not_of("geeksforgeeks");
    cout << "First unmatched character : ";
    cout << str[ch];
}

// Driver code
int main()
{
    string str("GeeksforGeeks");

    cout << "Original String : " << str << endl;
    find_last_not_ofDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks
First unmatched character : G
```

**语法 4:** 从索引 idx 中搜索不是 C 字符串 cstr
元素的最后一个字符

```cpp
size_type string::find_last_not_of (const string& str, size_type idx) const
cstr : Another C-string with the set of characters
to be used in the search.
idx : is the index number from where we have to
start finding first unmatched character.
```

**注意【cstr 不能是空指针(空)。** 

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for size_type string:: find_last_not_of
// (const char* cstr, size_type idx) const

#include <iostream>
using namespace std;

// Function to demonstrate find_last_not_of
void find_last_not_ofDemo(string str)
{
    // Finds last character in str from 5th index which
    // is not present in "geeksforgeeks"
    string::size_type ch = str.find_last_not_of("geeksForgeeks", 5);
    cout << "First unmatched character : ";
    cout << str[ch];
}

// Driver code
int main()
{
    string str("GeeksforGeeks");

    cout << "Original String : " << str << endl;
    find_last_not_ofDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks
First unmatched character : f
```

**语法 5:** 查找字符串中不等于字符 c 的最后一个字符。

```cpp
size_type string::find_last_not_of (const char* cstr) const
c: Character c with which contents of str are required to be compared.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for size_type string:: find_last_not_of (char c) const

#include <iostream>
using namespace std;

// Function to demonstrate find_last_not_of
void find_last_not_ofDemo(string str)
{
    // Finds last character in str which
    // is not equal to character 'G'
    string::size_type ch = str.find_last_not_of('G');
    cout << "First unmatched character : ";
    cout << str[ch];
}

// Driver code
int main()
{
    string str("GeeksforGeeks");

    cout << "Original String : " << str << endl;
    find_last_not_ofDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks
First unmatched character : s
```

**语法 6:** 从索引 idx 中查找字符串中不等于字符 c 的最后一个字符。

```cpp
size_type string::find_last_not_of (const char* cstr, size_type idx) const
c: Character c with which contents of str are required to be compared.
idx : index from where search of the first
unmatched character is to be started
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for size_type string::find_last_not_of
// (char c, size_type idx) const

#include <iostream>
using namespace std;

// Function to demonstrate find_last_not_of
void find_last_not_ofDemo(string str)
{
    // Finds last character in str from 6th index which
    // is not equal to character 'G'
    string::size_type ch = str.find_last_not_of('G', 6);
    cout << "First unmatched character : ";
    cout << str[ch];
}

// Driver code
int main()
{
    string str("GeeksforGeeks");

    cout << "Original String : " << str << endl;
    find_last_not_ofDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks
First unmatched character : o
```

**语法 7:** 从索引 idx 开始，搜索最后一个字符，该字符也不是字符数组 chars_len 字符的元素。

```cpp
size_type string::find_last_not_of (const char* chars, size_type idx, size_type
chars_len) const
*chars : is the character array with which 
searching of first unmatched is to be performed.
idx : index number in string
chars_len : is the character length in 
*chars to be picked for searching purpose
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code for size_type string::find_last_not_of
// (const char* chars, size_type idx, size_type chars_len) const

#include <iostream>
using namespace std;

// Function to demonstrate find_first_not_of
void find_last_not_ofDemo(string str)
{
    // Finds last character in str from 4th index which
    // is not equal to any of the first 3 characters from "svmnist"
    string::size_type ch = str.find_last_not_of("svmnist", 4, 3);
    cout << "First unmatched character : ";
    cout << str[ch];
}

// Driver code
int main()
{
    string str("GeeksforGeeks");

    cout << "Original String : " << str << endl;
    find_last_not_ofDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks
First unmatched character : k
```

本文由**萨基提瓦里**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。