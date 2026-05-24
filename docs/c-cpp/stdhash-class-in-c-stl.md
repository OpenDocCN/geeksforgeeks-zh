# STD::c++ STL 中的哈希类

> 原文:[https://www.geeksforgeeks.org/stdhash-class-in-c-stl/](https://www.geeksforgeeks.org/stdhash-class-in-c-stl/)

**哈希类**是默认可构造的，这意味着可以在没有任何参数或初始化值的情况下构造该对象。它用于获取传递给它的参数的哈希值。如果参数不变，值也不变。
**语法:**

```cpp
template <class T> struct hash;
```

**创建对象的语法:**

```cpp
hash<class template> object-name
```

**成员函数:**这个 Hash 类只有一个成员函数:

*   **运算符():**它返回给定参数的哈希值。

下面是哈希类的实现:
**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bitset>

// functional header
// for hash<class template> class
#include <functional>

#include <iostream>
#include <string>
#include <vector>

using namespace std;

// To demonstrate String Hashing
void stringHashing()
{

    // Get the string
    // to get its hash value
    string hashing1 = "Geeks";

    // Instantiation of Object
    hash<string> mystdhash;

    // Using operator() to get hash value
    cout << "String hash values: "
         << mystdhash(hashing1)
         << endl;
}

// To demonstrate BITSET Hashing
void bitsetHashing()
{

    // Get the BITSET
    // to get its hash value
    bitset<5> h_bitset("10101");

    // Instantiation of Object
    hash<bitset<5> > hash_bitset;

    // Using operator() to get hash value
    cout << "\nBitset 10101 hash value: "
         << hash_bitset(h_bitset) << endl;
}

// To demonstrate Vector<bool> Hashing
void vectorHashing()
{

    // Get the Vector<bool>
    // to get its hash value
    vector<bool>
        h_vecbool{ true, false,
                   true, false };

    // Instantiation of Object
    hash<vector<bool> > hash_vector_bool;

    // Using operator() to get hash value
    cout << "\nVector<bool> hash value: "
         << hash_vector_bool(h_vecbool)
         << endl;
}

// To demonstrate Char Hashing
void charHashing()
{

    // Get the char
    // to get its hash value
    char ch = 'a';

    // Instantiation of Object
    hash<char> hash_char;

    // Using operator() to get hash value
    cout << "\nChar hash values: "
         << hash_char(ch)
         << endl;
}

// Driver Code
int main()
{

    stringHashing();
    bitsetHashing();
    vectorHashing();
    charHashing();
}
```

**Output:** 

```cpp
String hash values: 4457761756728957899

Bitset 10101 hash value: 17123654466142159564

Vector hash value: 16935082123893034051

Char hash values: 97
```

**参考:**T2http://www.cplusplus.com/reference/functional/hash/