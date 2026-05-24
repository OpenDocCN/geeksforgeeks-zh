# strtool()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/strtoul-function-in-c-c/](https://www.geeksforgeeks.org/strtoul-function-in-c-c/)

C/C++ 中的**strtool()**函数，该函数根据给定的基数将 str 中字符串的初始部分转换为无符号长 int 值，该值必须介于 2 和 36 之间(含 2 和 36)，或者是特殊值 0。该函数丢弃任何空白字符，直到找到第一个非空白字符，然后尽可能多的字符形成一个有效的基数为 n 的无符号整数表示，并将它们转换为整数值。

**语法:**

```cpp
unsigned long int strtoul(const char *str, char **end, int base)
```

**参数:**该功能接受三个强制参数，如下所述:

*   **字符串:**指向要解释的空终止字节字符串的指针
*   **结束:**指向字符指针的指针(对 char*类型对象的引用)
*   **基数:**解释整数值的基数

**返回值:**该函数返回如下两个值:

*   成功后，它返回一个与字符串内容对应的整数值。
*   如果没有进行有效的转换，则返回 0。

以下程序说明了上述功能:

**程序 1:**

## C++

```cpp
// C++ program to illustrate the
// strtoul() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initializing the string
    char str[256] = "90600 Geeks For Geeks";

    // reference pointer
    char* end;
    long result;

    // finding the unsigned long
    // integer with base 36
    result = strtoul(str, &end, 36);

    // printing the unsigned number
    cout << "The unsigned long integer is : "
         << result << endl;
    cout << "String in str is : " << end;

    return 0;
}
```

**Output:** 

```cpp
The unsigned long integer is : 15124320
String in str is :  Geeks For Geeks
```

**程序 2:**

## C++

```cpp
// C++ program to illustrate the
// strtoul() function with
// different bases
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initializing the string
    char str[256] = "12345 GFG";

    // reference pointer
    char* end;
    long result;

    // finding the unsigned long integer
    // with base 36
    result = strtoul(str, &end, 0);
    cout << "The unsigned long integer is : "
         << result << endl;
    cout << "String in str is : " << end << endl;

    // finding the unsigned long integer
    // with base 12
    result = strtoul(str, &end, 12);
    cout << "The unsigned long integer is : "
         << result << endl;
    cout << "String in str is : " << end << endl;

    // finding the unsigned long integer
    // with base 30
    result = strtoul(str, &end, 30);
    cout << "The unsigned long integer is : "
         << result << endl;
    cout << "String in str is : " << end << endl;

    return 0;
}
```

**Output:** 

```cpp
The unsigned long integer is : 12345
String in str is :  GFG
The unsigned long integer is : 24677
String in str is :  GFG
The unsigned long integer is : 866825
String in str is :  GFG
```