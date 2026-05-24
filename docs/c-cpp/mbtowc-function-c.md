# C

中的 mbtowc 功能

> 原文:[https://www.geeksforgeeks.org/mbtowc-function-c/](https://www.geeksforgeeks.org/mbtowc-function-c/)

将多字节序列转换为宽字符。pmb 指向的多字节字符被转换为 wchar_t 类型的值，并存储在 pwc 指向的位置。函数返回多字节字符的字节长度。
mbtowc 有自己的内部移位状态，只在需要时通过调用这个函数来改变。使用空指针作为 pmb 对函数的调用会重置状态(并返回多字节字符是否依赖于状态)。
该函数的行为取决于所选 C 语言环境(C 本地化库)的 LC_CTYPE 类别。

**语法**:

```cpp
pwc: Pointer to an object of type wchar_t.
Alternatively, this argument can be a null pointer, 
in which case the function does not store the wchar_t translation, 
but still returns the length in bytes of the multibyte character.

pmb: Pointer to the first byte of a multibyte character.
Alternatively, this argument can be a null pointer, 
in which case the function resets its internal shift 
state to the initial value and returns whether 
multibyte characters have a state-dependent encoding.

max: Maximum number of bytes of pmb 
to consider for the multibyte character.

Return Value: If the argument passed as pmb is not a null pointer, 
the size in bytes of the multibyte character pointed by pmb is returned 
when it forms a valid multibyte character and is not the terminating 
null character. If it is the terminating null character, the function 
returns zero, and in the case they do not form a valid multibyte character, -1 is returned.
If the argument passed as pmb is a null pointer, 
the function returns a nonzero value if multibyte character 
encodings are state-dependent, and zero otherwise.

```

```cpp
// C program to illustrate mbtowc
// function
#include <stdio.h>
#include <stdlib.h> // function containing mbtowc & wchar_t(C) function

void mbtowc_func(const char* pt, size_t max)
{
    int length;

    // this is a typedef of an integral type
    wchar_t dest;

    // reset mbtowc
    mbtowc(NULL, NULL, 0);

    while (max > 0) {
        length = mbtowc(&dest, pt, max);
        if (length < 1) {
            break;
        }

        // printing each character in square braces
        printf("[%lc]", dest);
        pt += length;
        max -= length;
    }
}

int main()
{
    const char str[] = "geeks portal";

    mbtowc_func(str, sizeof(str));

    return 0;
}
```

输出:

```cpp
[g][e][e][k][s][ ][p][o][r][t][a][l]

```