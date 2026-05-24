# c++ 中的字符串查找

> 原文:[https://www.geeksforgeeks.org/string-find-in-cpp/](https://www.geeksforgeeks.org/string-find-in-cpp/)

[字符串](https://www.geeksforgeeks.org/stdstring-class-in-c/) find 用于查找被调用的指定字符串中子字符串的第一次出现。它从给定的起始位置返回字符串中第一个出现的子字符串的索引。起始位置的默认值为 0。

**功能模板:**

*   size_t find (const string& str，size _ t pos = 0)；
*   size_t find (const char* s，size _ t pos = 0)；

**功能参数:**

*   字符串:要搜索的子字符串。
*   s:要搜索的子字符串，给定为 C 风格的字符串。
*   位置:字符串搜索开始的初始位置。

**功能返回:**

*   该函数返回子字符串第一次出现的索引，如果找不到子字符串，则返回 string::npos(string::pos 是静态成员，其值是 size_t 数据结构的最大值)。

```cpp
// CPP program to demonstrate working of string
// find to search a string
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string str = "geeksforgeeks a computer science";
    string str1 = "geeks";

    // Find first occurrence of "geeks"
    size_t found = str.find(str1);
    if (found != string::npos)
        cout << "First occurrence is " << found << endl;

    // Find next occurrence of "geeks". Note here we pass
    // "geeks" as C style string.
    char arr[] = "geeks";
    found = str.find(arr, found+1);
    if (found != string::npos)
        cout << "Next occurrence is " << found << endl;

    return 0;
}
```

**Output:**

```cpp
First occurrence is 0
Next occurrence is 8

```

**我们也可以用它来查找一个字符的出现:**
在下面的语法中，注意 c 是一个字符。

*   size_t find (const char c，size _ t pos = 0)；

```cpp
// CPP program to demonstrate working of string
// find to search a string
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string str = "geeksforgeeks a computer science";
    char c = 'g';

    // Find first occurrence of 'g'
    size_t found = str.find(c);
    if (found != string::npos)
        cout << "First occurrence is " << found << endl;

    // Find next occurrence of 'g'
    found = str.find(c, found+1);
    if (found != string::npos)
        cout << "Next occurrence is " << found << endl;

    return 0;
}
```

**Output:**

```cpp
First occurrence is 0
Next occurrence is 8

```

**我们也可以搜索部分字符串**
在下面的语法中，注意 n 是要匹配的字符数。

*   size_t find (const char *str，size_t pos，size _ t n)；

```cpp
// CPP program to demonstrate working of string
// find to search a string
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string str = "geeksforgeeks a computer science";

    // Only search first 5 characters of "geeks.practice"
    size_t found = str.find("geeks.practice", 0, 5);
    if (found != string::npos)
        cout << found << endl;

    return 0;
}
```

**Output:**

```cpp
0

```