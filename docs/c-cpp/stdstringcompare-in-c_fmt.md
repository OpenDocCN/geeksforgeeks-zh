# std::string::compare() 在 C++ 中

> 哎哎哎: https://www.geeksforgeeks.org/stdstringcompare-in-c/

`compare()` 是 `string` 类的公共成员函数。它将字符串对象（或子字符串）的值与其参数指定的字符序列进行比较。
`compare()` 可以为每个字符串处理多个参数，这样就可以通过其索引和长度来指定子字符串。

**返回类型:** `compare()` 返回整数值而不是布尔值。

## 字符串的 `compare()` 语法

### 1. 语法 1
将字符串 `*this` 与字符串 `str` 进行比较。

```cpp
int string::compare (const string& str) const
```
返回值：
- `0`：如果两个字符串相等。
- 一个 **<** `0` 的值：如果 `*this` 比 `str` 短，或者第一个不匹配的字符比 `str` 中的小。
- 一个 **>** `0` 的值：如果 `*this` 比 `str` 长，或者第一个不匹配的字符比 `str` 中的大。

```cpp
// CPP code for demonstrating 
// string::compare (const string& str) const

#include<iostream>
using namespace std;

void compareOperation(string s1, string s2)
{
    // returns a value < 0 (s1 is smaller then s2)
    if((s1.compare(s2)) < 0)
        cout << s1 << " is smaller than " << s2 << endl;

    // returns 0(s1, is being comapared to itself)
    if((s1.compare(s1)) == 0)
        cout << s1 << " is equal to " << s1 << endl;
    else
        cout << "Strings didn't match ";
}

// Driver Code
int main()
{
    string s1("Geeks");
    string s2("forGeeks");
    compareOperation(s1, s2);

    return 0; 
}
```

输出:

```cpp
Geeks is smaller than forGeeks
Geeks is equal to Geeks
```

### 2. 语法 2
将字符串 `*this` 中最多 `len` 个字符（从索引 `idx` 开始）与字符串 `str` 进行比较。

```cpp
int string::compare (size_type idx, size_type len, const string& str) const
```
如果 `index > size()` 则抛出 `out_of_range`。

```cpp
// CPP code to demonstrate 
// int string::compare (size_type idx, size_type len, 
// const string& str) const

#include<iostream>
using namespace std;

void compareOperation(string s1, string s2)
{
    // Compares 5 characters from index number 3 of s2 with s1
    if((s2.compare(3, 5, s1)) == 0)
        cout << "Here, "<< s1 << " are " << s2;
    else
        cout << "Strings didn't match ";
}
// Driver Code
int main()
{
    string s1("Geeks");
    string s2("forGeeks");
    compareOperation(s1, s2);

    return 0; 
}
```

输出:

```cpp
Here, Geeks are forGeeks
```

### 3. 语法 3
将字符串 `*this` 中最多 `len` 个字符（从索引 `idx` 开始）与字符串 `str` 中最多 `str_len` 个字符（从索引 `str_idx` 开始）进行比较。

```cpp
int string::compare (size_type idx, size_type len, const string& 
str, size_type str_idx, size_type str_len) const
```
如果 `idx > size()` 则抛出 `out_of_range`。
如果 `str_idx > str.size()` 则抛出 `out_of_range`。

```cpp
// CPP code to demonstrate 
// int string::compare (size_type idx, size_type len, const string& 
// str, size_type str_idx, size_type str_len) const

#include<iostream>
using namespace std;

void compareOperation(string s1, string s2)
{
    // Compares 5 characters from index number 0 of s1 with
    // 5 characters from index 3 of s2
    if((s1.compare(0, 5, s2, 3, 5)) == 0)
        cout << "Welcome to " << s1 << s2 << " World";
    else
        cout << "Strings didn't match ";
}
// Driver Code
int main()
{
    string s1("Geeks");
    string s2("forGeeks");
    compareOperation(s1, s2);

    return 0; 
}
```

输出:

```cpp
Welcome, to GeeksforGeeks World
```

### 4. 语法 4
将字符串 `*this` 的字符与 C 风格字符串 `cstr` 的字符进行比较。

```cpp
int string::compare (const char* cstr) const
```

```cpp
// CPP code to demonstrate
// int string::compare (const char* cstr) const

#include<iostream>
using namespace std;

void compareOperation(string s1, string s2)
{
    // returns < 0 (s1 < "GeeksforGeeks")
    if((s1.compare("GeeksforGeeks")) < 0)
        cout << s1 << " is smaller than string " << "GeeksforGeeks";

    //returns 0 (s2 is "forgeeks")
    if((s2.compare("forGeeks")) == 0)
        cout << endl << s2 << " is equal to string " << s2;
    else
        cout << "Strings didn't match ";
}
// Driver Code
int main()
{
    string s1("Geeks");
    string s2("forGeeks");
    compareOperation(s1, s2);

    return 0; 
}
```

输出:

```cpp
Geeks is smaller than string GeeksforGeeks
forGeeks is equal to string forGeeks
```

### 5. 语法 5
将字符串 `*this` 中最多 `len` 个字符（从索引 `idx` 开始）与 C 风格字符串 `cstr` 的所有字符进行比较。

```cpp
int string::compare (size_type idx, size_type len, const char* cstr) const
```
请注意，`cstr` 不能是空指针(`null`)。

```cpp
// CPP code to demonstrate 
// int string::compare (size_type idx, size_type len, 
// const char* cstr) const
#include<iostream>
using namespace std;

void compareOperation(string s1)
{
    // Compares 5 characters from 0 index of s1 with "Geeks"
    if((s1.compare(0, 5, "Geeks")) == 0)
        cout << s1 << " are " << "awesome people";
    else
        cout << "Strings didn't match ";
}

// Driver Code
int main()
{
    string s1("Geeks");
    compareOperation(s1);

    return 0; 
}
```

输出:

```cpp
Geeks are awesome people
```

### 6. 语法 6
将字符串 `*this` 中最多 `len` 个字符（从索引 `idx` 开始）与字符数组 `chars` 中的 `chars_len` 个字符进行比较。

```cpp
int string::compare (size_type idx, size_type len, const char* chars, 
size_type chars_len)const
```
请注意，字符必须至少包含 `chars_len` 字符。字符可以有任意值。因此，`'\0'` 没有特殊含义。

```cpp
// CPP code to demonstrate 
// int string::compare (size_type idx, size_type len, 
// const char* chars, size_type chars_len)const

#include<iostream>
using namespace std;

void compareOperation(string s1, string s2)
{
    // Compares 5 characters from 0 index of s1 with 
    // 5 characters of string "Geeks"
    if((s1.compare(0, 5, "Geeks", 5)) == 0)
        cout << "This is " << s1 <<  s2 ;
    else
        cout << "Strings didn't match ";
}

// Driver Code
int main()
{
    string s1("Geeks");
    string s2("forGeeks");
    compareOperation(s1, s2);

    return 0; 
}
```

输出:

```cpp
This is GeeksforGeeks
```

本文由**萨基提瓦里**供稿。如果你喜欢极客（我们知道你喜欢！）并愿意投稿，也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者将文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。