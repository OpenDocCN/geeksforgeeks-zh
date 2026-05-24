# c++ 中的子串

> 原文:[https://www.geeksforgeeks.org/substring-in-cpp/](https://www.geeksforgeeks.org/substring-in-cpp/)

在 C++ 中，std::substr()是用于字符串处理的预定义函数。 **string.h** 是字符串函数所需的头文件。
该函数以两个值 **pos** 和 **len** 为参数，返回一个新构造的字符串对象，其值初始化为该对象的子字符串的副本。字符串的复制从*位置*开始，一直到*位置+镜头*表示**【位置，位置+镜头)**。
**要点:**

1.  第一个字符的索引是 0(不是 1)。
2.  如果 **pos** 等于字符串长度，则函数返回一个空字符串。
3.  如果**位置**大于字符串长度，则抛出 _ 超出范围。如果发生这种情况，字符串中没有变化。
4.  如果请求的子字符串 **len** 大于字符串的大小，则返回的子字符串为**【位置，大小())**。

**语法:**

```cpp
string substr (size_t pos, size_t len) const;
Parameters:
pos: Position of the first character to be copied.
len: Length of the sub-string.
size_t: It is an unsigned integral type.

Return value: It returns a string object.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate substr()
#include <string.h>
#include <iostream>
using namespace std;

int main()
{
    // Take any string
    string s1 = "Geeks";

    // Copy three characters of s1 (starting
    // from position 1)
    string r = s1.substr(1, 3);

    // prints the result
    cout << "String is: " << r;

    return 0;
}
```

**输出:**

```cpp
String is: eek
```

**应用:**

1.  **如何获取字符后的子串？**
    在这个例子中，给出了一个字符串和一个字符，你必须在给定的字符后面打印子字符串。
    提取字符串*【狗:猫】*中*:*之后的所有内容。

## C++

```cpp
// CPP program to illustrate substr()
#include <string.h>
#include <iostream>
using namespace std;

int main()
{
    // Take any string
    string s = "dog:cat";

    // Find position of ':' using find()
    int pos = s.find(":");

    // Copy substring after pos
    string sub = s.substr(pos + 1);

    // prints the result
    cout << "String is: " << sub;

    return 0;
}
```

**Output**

```cpp
String is: cat
```

2.**如何在字符前获取** **子串？**
在这种情况下，给出一个字符串和一个字符，您必须在给定字符后打印子字符串。
提取字符串“狗:猫”中“:”前的所有内容。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate substr()
#include <string.h>
#include <iostream>
using namespace std;

int main()
{
    // Take any string
    string s = "dog:cat";

    // Find position of ':' using find()
    int pos = s.find(":");

    // Copy substring before pos
    string sub = s.substr(0 , pos);

    // prints the result
    cout << "String is: " << sub;

    return 0;
}
```

**Output**

```cpp
String is: dog
```

3.[打印给定字符串的所有子字符串](https://www.geeksforgeeks.org/program-print-substrings-given-string/)
4。[代表数字的字符串的所有子字符串的总和](https://www.geeksforgeeks.org/sum-of-all-substrings-of-a-string-representing-a-number/)