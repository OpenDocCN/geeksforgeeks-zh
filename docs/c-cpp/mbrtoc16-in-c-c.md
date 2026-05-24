# 带示例的 C/C++ 中的 mbrtoc16()

> 原文:[https://www.geeksforgeeks.org/mbrtoc16-in-c-c/](https://www.geeksforgeeks.org/mbrtoc16-in-c-c/)

**MBR TOC 16()**是 C/C++ 中的一个内置函数，它将一个窄的多字节字符转换为 16 位字符表示。在 C++ 的 **uchar.h** 头文件中定义。

**语法**:

```cpp
ssize_t mbrtoc16( char16_t* pc16, const char* s, size_t n, mbstate_t* ps);
```

**参数**:该功能接受四个强制参数，描述如下:

*   **s** :指定要转换的多字节字符。
*   **pc16** :指定存储结果 16 位字符的存储位置。
*   **n** :指定要转换的最大字节数，单位为 s。
*   **ps** :指定解释多字节字符串时使用的 mbstate_t 对象。

**返回值**:该函数返回如下五个值:

*   如果转换后的字符为空字符，则为 0。
*   成功转换为 16 位字符的多字节字符的字节数(最多 n 个)。
*   -3 如果多 char16_t 字符(例如代理项对)的下一个 char16_t 现在已经写入*pc16。在这种情况下，不会从输入中处理任何字节。
*   -2 如果接下来的 n 个字节构成了一个不完整的、但迄今为止有效的多字节字符。在这种情况下，不会向*pc16 写入任何内容。
*   如果发生编码错误，则为-1。在这种情况下，没有任何内容被写入*pc16，errno 被设置为 **EILSEQ** ，并且*ps 的值未指定。

下面的程序说明了上述功能。

**程序 1** :

```cpp
// C++ program to illustrate the
// mbrtoc16() function
#include <cstdio>
#include <cstdlib>
#include <iostream>
#include <uchar.h>
#include <wchar.h>
using namespace std;

int main(void)
{
    char16_t pc16;
    char s[] = "G";
    mbstate_t ps{};
    int length;

    // initializing the function
    length = mbrtoc16(&pc16, s, MB_CUR_MAX, &ps);

    if (length < 0) {
        perror("mbrtoc16() fails to convert");
        exit(-1);
    }

    cout << "Multibyte string = " << s << endl;
    cout << "Length = " << length << endl;
    printf("16-bit character = 0g%02hd\n", pc16);
}
```

**Output:**

```cpp
Multibyte string = G
Length = 1
16-bit character = 0g71

```

**程序 2** :

```cpp
// C++ program to illustrate the
// mbrtoc16() function
#include <cstdio>
#include <cstdlib>
#include <iostream>
#include <uchar.h>
#include <wchar.h>
using namespace std;

int main(void)
{
    char16_t pc16;
    char s[] = "";
    mbstate_t ps{};
    int length;
    // initializing the function
    length = mbrtoc16(&pc16, s, MB_CUR_MAX, &ps);

    if (length < 0) {
        perror("mbrtoc16() fails to convert");
        exit(-1);
    }

    cout << "Multibyte string = " << s << endl;
    cout << "Length = " << length << endl;
    printf("16-bit character = 1e%04xy\n", pc16);
}
```

**Output:**

```cpp
Multibyte string = 
Length = 0
16-bit character = 1e0000y

```