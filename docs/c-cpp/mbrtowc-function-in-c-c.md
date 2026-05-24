# mbrtowc()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/mbrtowc-function-in-c-c/](https://www.geeksforgeeks.org/mbrtowc-function-in-c-c/)

C/C++ 中的 **mbrtowc()** 函数将多字节序列转换为宽字符。该函数返回多字节字符的字节长度。s 所指向的多字节字符被转换为 wchar_t 类型的值，并存储在 pwc 所指向的位置。如果 s 指向空字符，则该函数重置移位状态，并在 pwc 存储宽空字符后返回零。

**语法:**

```cpp
size_t mbrtowc (wchar_t* pwc, const char* pmb, size_t max, mbstate_t* ps)
```

**参数:**该函数接受如下所述的四个参数:

*   **pwc :** 指针，指向结果宽字符将被写入的位置
*   **s :** 指向用作输入的多字节字符串的指针
*   **n :** 可以检查的字节数限制(s)
*   **ps :** 指针，指向解释多字节字符串时使用的转换状态

**返回值:**该函数返回如下四个值:

1.  如果为空宽字符，或者 pmb 为空指针，则函数返回 0
2.  从 s 成功转换的多字节字符的字节数[1…n]
3.  如果 pmb 的最大前几个字符构成不完整的多字节字符，则该函数返回 length-2
4.  否则，函数返回 length-1，并将 errno 设置为 EILSEQ

**注意:**可能返回的值都不小于零。

以下程序说明了上述功能:
**程序 1:**

```cpp
// C++ program to illustrate
// mbrtowc() function
#include <bits/stdc++.h>
using namespace std;

// Function to convert multibyte
// sequence to wide character
void print_(const char* s)
{
    // initial state
    mbstate_t ps = mbstate_t();

    // length of the string
    int length = strlen(s);

    const char* n = s + length;
    int len;
    wchar_t pwc;

    // printing each bytes
    while ((len = mbrtowc(&pwc, s, n - s, &ps)) > 0) {
        wcout << "Next " << len << 
        " bytes are the character " << pwc << '\n';
        s += len;
    }
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.utf8");

    // UTF-8 narrow multibyte encoding
    const char* str = u8"z\u00df\u6c34\U0001d10b";

    print_(str);
}
```

**Output:**

```cpp
Next 1 bytes are the character z
Next 2 bytes are the character Ã?
Next 3 bytes are the character æ°´
Next 4 bytes are the character ð??

```

**程序 2:**

```cpp
// C++ program to illustrate
// mbrtowc() function
// with different UTF-8 characters
#include <bits/stdc++.h>
using namespace std;

// Function to convert multibyte
// sequence to wide character
void print_(const char* s)
{
    // initial state
    mbstate_t ps = mbstate_t();

    // length of the string
    int length = strlen(s);

    const char* n = s + length;
    int len;
    wchar_t pwc;

    // printing each bytes
    while ((len = mbrtowc(&pwc, s, n - s, &ps)) > 0) {
        wcout << "Next " << len << 
        " bytes are the character " << pwc << '\n';
        s += len;
    }
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.utf8");

    // UTF-8 narrow multibyte encoding
    const char* str = u8"\xE2\x88\x83y\xE2\x88\x80x\xC2\xAC";

    print_(str);
}
```

**Output:**

```cpp
Next 3 bytes are the character â??
Next 1 bytes are the character y
Next 3 bytes are the character â??
Next 1 bytes are the character x
Next 2 bytes are the character Â¬

```