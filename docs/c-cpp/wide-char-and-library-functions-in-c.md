# c++ 中的宽字符和库函数

> 原文:[https://www . geesforgeks . org/wide-char-and-library-functions-in-c/](https://www.geeksforgeeks.org/wide-char-and-library-functions-in-c/)

宽字符类似于字符数据类型，除了宽字符占用两倍空间，因此可以采用更大的值。char 可以取 256 个值，对应于 ASCII 表中的条目。另一方面，宽字符可以采用 65536 个值，这对应于 UNICODE 值，UNICODE 值是一个最新的国际标准，它允许对几乎所有语言和常用符号的字符进行编码。

1.  就像字符常量的类型是 char 一样，宽字符的类型是 wchar_t。
2.  根据所使用的编译器，该数据类型占用 2 或 4 个字节。
3.  当使用像日语这样的国际语言时，通常使用 wchar_t 数据类型。

下面是一个简单的 C++ 实现来展示 wchar_t 是如何使用的:

```cpp
// An example C++ program to demonstrate use of wchar_t
#include <iostream>
using namespace std;

int main()
{
    wchar_t w  = L'A';
    cout << "Wide character value:: " << w << endl ;
    cout << "Size of the wide char is:: " << sizeof(w);
    return 0;
}
```

输出:

```cpp
Wide character value:: 65
Size of the wide char is:: 4

```

*   l 是宽字符文字和宽字符串文字的前缀，它告诉编译器字符或字符串属于宽字符类型。
*   在操作宽字符类型时，在扫描(wcin)或打印(wcout)等操作中，w 是前缀。

**宽字符型数组或字符串:**
就像字符型数组字符串一样，也可以有宽字符型数组字符串。下面是显示宽字符类型数组字符串的 C++ 实现:

```cpp
// An example C++ program to demonstrate use
// of wchar_t in array
#include <iostream>
using namespace std;

int main()
{
    // char type array string
    char caname[] = "geeksforgeeks" ;
    cout << caname << endl ;

    // wide-char type array string
    wchar_t waname[] = L"geeksforgeeks" ;
    wcout << waname << endl;

    return 0;
}
```

输出:

```cpp
geeksforgeeks
geeksforgeeks

```

输出是相同的，但唯一的区别是宽字符数组使用两倍的内存来编码每个字符。

**宽字符数组字符串的函数:**
大部分宽字符数组字符串的函数都是在头文件 cwchar 中定义的。

**wcslen() :** 语法:size _ t wcs len(const wchar _ t * wcs)；
返回宽字符串的长度。这是 strlen 的宽字符等价物。

下面是一个简单的 C++ 实现，展示了如何获取宽字符数组字符串的长度。

```cpp
// An example C++ program to demonstrate use
// of wcslen()
#include <iostream>
#include<cwchar>
using namespace std;

int main()
{
    // wide-char type array string
    wchar_t waname[] = L"geeksforgeeks" ;

    wcout << L"The length of '" << waname
          << L"' is " << wcslen(waname) << endl;

    return 0;
}
```

输出:

```cpp
The length of 'geeksforgeeks' is 13

```

**wcscpy() :** 语法:wchar _ t * wcs cpy(wchar _ t * strDestination，const wchar _ t * strSource)；
wcscpy()代表宽字符串副本。它将 strSource 指向的宽字符串复制到 strDestination 指向的宽字符数组中。这是 strcpy 的宽字符等价物。
下面是一个简单的 C++ 实现，展示了 wcscpy 的使用:

```cpp
// An example C++ program to demonstrate use
// of wcscpy()
#include <iostream>
#include<cwchar>
using namespace std;

int main()
{
    wchar_t waname[] = L"geeksforgeeks" ;
    wchar_t wacopy[14];
    wcscpy(wacopy, waname);
    wcout << L"Original = " << waname
          << L"\nCopy =  " << wacopy << endl;

    return 0;
}
```

输出:

```cpp
Original = geeksforgeeks
Copy =  geeksforgeeks

```

**wcscat() :** 语法:wchar _ t * wcscat(wchar _ t * strDestination，const wchar _ t * strSource)；
wcscat()代表宽字符串连接。将 strSource 宽字符串的副本追加到 strDestination 宽字符串。这是 strcat 的宽字符等价物。

下面是一个简单的 C++ 实现，展示了 wcscat 的使用:

```cpp
// An example C++ program to demonstrate use
// of wcscat()
#include <iostream>
#include<cwchar>
using namespace std;

int main()
{
    wchar_t string1[] = L"geeksforgeeks" ;
    wchar_t string2[] = L" is for Geeks" ;

    wcscat(string1, string2);

    wcout << L"Concatenated wide string is = "
          << string1 << endl;

    return 0;
}
```

输出:

```cpp
Concatenated wide string is = geeksforgeeks is for Geeks

```

**wcscmp() :** 语法:int wcscmp(const wchar_t* wcs1，const wchar _ t * wcs 2)；
wcscmp()代表宽字符串比较。如果 wcs1 和 wcs2 相等，则返回 0；如果第一个不匹配的宽字符在 wcs1 中的值大于 wcs2 中的值，则返回大于零的值。如果第一个不匹配的宽字符在 wcs1 中的值小于 wcs2 中的值，则返回小于零的值。这是 strcmp 的宽字符等价物。

下面是一个简单的 C++ 实现来展示 wcscmp 的使用:

```cpp
// An example C++ program to demonstrate use
// of wcscmp()
#include <iostream>
#include<cwchar>
using namespace std;

int main()
{
    wchar_t string1[] = L"geeksforgeeks" ;
    wchar_t string2[] = L"GEEKS" ;
    wcout << L"Comparison1 = "
          << wcscmp(string1, string2) << endl;
    wcout << L"Comparison2 = "
          << wcscmp(string1, string1) << endl;
    wcout << L"Comparison3 = "
          << wcscmp(string2, string1) << endl;
    return 0;
}
```

输出:

```cpp
Comparison1 = 1
Comparison2 = 0
Comparison3 = -1

```

**wcstok() :** 语法:wchar_t* wcstok( wchar_t* str，const wchar_t* delim，wchar _ t * * ptr)；
wcstok()代表宽字符串标记化。在字符串指向的以 null 结尾的宽字符串中查找下一个标记。分隔符由 delim 指向的以 null 结尾的宽字符串标识。
str–指向要标记的以 null 结尾的宽字符串的指针。
delim–指向以空结尾的宽字符串的指针，用于标识分隔符。
ptr–wchar _ t *类型对象的指针，wcstok 使用它来存储其内部状态。
这是 strtok()的宽字符等价物。
下面是一个简单的 C++ 实现，展示了 wcstok 的使用:

```cpp
// An example C++ program to demonstrate use
// of wcstok()
#include <iostream>
#include<cwchar>
using namespace std;

int main()
{
    wchar_t string[] = L"geeksforgeeks,is,for,GEEKS" ;

    wchar_t* internal_state;

    wchar_t delim[] = L"," ;
    wchar_t* token  = wcstok(string, delim, &internal_state);

    while (token)
    {
        wcout << token << endl;
        token = wcstok(NULL, delim, &internal_state);
    }

    return 0;
}
```

输出:

```cpp
geeksforgeeks
is
for
GEEKS

```

**wcsncpy() :** 语法:wchar_t* wcsncpy(wchar_t*目的地，const wchar_t*源，size _ t n)；
将源的前 n 个宽字符复制到目标。如果在复制 n 个字符之前找到了源宽字符串的结尾，目标将被填充额外的空宽字符，直到总共 n 个字符。这是 strncpy()的宽字符等价物。

下面是一个简单的 C++ 实现，展示了 wcsncpy 的使用:

```cpp
// An example C++ program to demonstrate use
// of wcsncpy()
#include <iostream>
#include<cwchar>
using namespace std;

int main()
{
    wchar_t string1[] = L"Geeks For Geeks";
    wchar_t string2[20];
    wchar_t string3[20];

    wcsncpy(string2, string1, 20);

    // partial copy
    wcsncpy(string3, string2, 5);

    string3[5] = L'\0';   // null character manually added

    wcout << string1 << endl << string2
          << endl << string3 ;

    return 0;
}
```

输出:

```cpp
Geeks For Geeks
Geeks For Geeks
Geeks

```

**wcs tr():**语法:const wchar _ t * wcs tr(const wchar _ t * wcs S1，const wchar _ t * wcs S2)；
返回 wcs1 中第一个 wcs2 的指针。如果 wcs2 不是 wcs1 的一部分，它将返回空指针。这里，wcs1 是要扫描的宽字符串，wcs2 包含要匹配的序列。这是 strstr()的宽字符等价物。

下面是一个简单的 C++ 实现来展示 wcsstr 的使用:

```cpp
// An example C++ program to demonstrate use
// of wcsstr()
#include <iostream>
#include<cwchar>
using namespace std;

int main()
{
    wchar_t string1[] = L"Geeks Are Geeks";
    wchar_t* string2 = wcsstr(string1, L"Are");
    wcsncpy(string2, L"For", 3);
    wcout << string1 << endl;
    return 0;
}
```

输出:

```cpp
Geeks For Geeks

```

**参考:**T2[http://www.cplusplus.com/reference/cwchar/](http://www.cplusplus.com/reference/cwchar/)

本文由 [**MAZHAR IMAM KHAN**](https://www.linkedin.com/in/mazhar-imam-khan-95a34ab3/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。