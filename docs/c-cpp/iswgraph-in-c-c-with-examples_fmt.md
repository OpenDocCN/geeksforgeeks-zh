# C/C++ 中的 `iswgraph()` 函数详解

> 原文: [https://www.geeksforgeeks.org/iswgraph-in-c-c-with-examples/](https://www.geeksforgeeks.org/iswgraph-in-c-c-with-examples/)

## 介绍

`iswgraph()` 是 C/C++ 中的一个内置函数，用于检查给定的宽字符是否具有图形表示。它在 C++ 的 `<cwctype>` 头文件中定义。

默认情况下，以下字符被认为是图形字符：
*   数字 (0 至 9)
*   大写字母 (A 至 Z)
*   小写字母 (a 至 z)
*   标点符号 (!"#$%&'()*+,-./:;?@[\]^_`{|}~)

## 语法

```cpp
int iswgraph(wint_t ch);
```

## 参数

该函数接受一个强制参数 `ch`，它指定了要检查是否具有图形表示的宽字符。

## 返回值

函数返回以下两个值之一：
*   如果 `ch` 是图形表示字符，则返回一个非零值。
*   如果 `ch` 不是图形表示字符，则返回 0。

## 示例程序

下面的程序说明了 `iswgraph()` 函数的功能。

### 程序 1

```cpp
// C++ program to illustrate
// iswgraph() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{
    wchar_t ch1 = '?';
    wchar_t ch2 = ' ';

    // Function to check if the character
    // has a graphical representation or not
    if (iswgraph(ch1))
        wcout << ch1 << " has graphical representation ";
    else
        wcout << ch1 << " does not have graphical representation ";
    wcout << endl;

    if (iswgraph(ch2))
        wcout << ch2 << " has graphical representation ";
    else
        wcout << ch2 << " does not have graphical representation ";

    return 0;
}
```

**输出：**

```cpp
? has graphical representation 
  does not have graphical representation
```

### 程序 2

```cpp
// C++ program to illustrate
// iswgraph() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{
    wchar_t ch1 = ' ';
    wchar_t ch2 = '3';

    // Function to check if the character
    // has a graphical representation or not
    if (iswgraph(ch1))
        wcout << ch1 << " has graphical representation ";
    else
        wcout << ch1 << " does not have graphical representation ";
    wcout << endl;

    if (iswgraph(ch2))
        wcout << ch2 << " has graphical representation ";
    else
        wcout << ch2 << " does not have graphical representation ";

    return 0;
}
```

**输出：**

```cpp
  does not have graphical representation 
3 has graphical representation
```