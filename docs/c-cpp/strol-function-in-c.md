# strol()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/strol-function-in-c/](https://www.geeksforgeeks.org/strol-function-in-c/)

C++ 中的 **strtol()** 函数将字符串的内容解释为指定基数的整数，并将其值作为长整型返回。此函数还设置一个指向字符串最后一个有效数字字符后的第一个字符的结束指针，如果没有这样的字符，则指针设置为空。该功能在 **cstdlib** 头文件中定义。
**语法:**

```cpp
long int strtol(const char* str, char** end, int base)
```

**参数:**该函数接受三个强制参数，如下所述。

*   **字符串:**由整数组成字符串。
*   **end:** 这是对 char*类型对象的引用。end 的值由函数设置为字符串中最后一个有效数字字符之后的下一个字符。如果没有使用，这个参数也可以是空指针。
*   **基数:**表示决定字符串中有效字符及其解释的数字基数(基数)

**返回类型:**函数返回两种类型的值，描述如下:

*   如果发生了有效的转换，则该函数将转换后的整数作为*长整数*值返回。
*   如果无法执行有效转换，则返回零值。

下面的程序说明了上述功能。
**节目一:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// strtol() function
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    int base = 10;
    char str[] = "123abc";
    char* end;
    long int num;

    // Function used to convert string
    num = strtol(str, &end, base);

    cout << "Given  String = " << str << endl;
    cout << "Number with base 10 in string " << num << endl;
    cout << "End String points to " << end << endl
         << endl;

    // in this case the end pointer points to null
    strcpy(str, "12345");

    // prints the current string
    cout << "Given String = " << str << endl;

    // function used
    num = strtol(str, &end, base);

    // prints the converted integer
    cout << "Number with base 10 in string " << num << endl;
    if (*end) {
        cout << end;
    }
    else {
        cout << "Null pointer";
    }
    return 0;
}
```

**Output:** 

```cpp
Given  String = 123abc
Number with base 10 in string 123
End String points to abc

Given String = 12345
Number with base 10 in string 12345
Null pointer
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// strtol() function Program to
// convert multiple values at different base
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    char str[] = "100 ab 123 1010";
    char* end;
    long int a, b, c, d;

    // base 10
    a = strtol(str, &end, 10);

    // base 16
    b = strtol(end, &end, 16);

    // base 8
    c = strtol(end, &end, 8);

    // base 2
    d = strtol(end, &end, 2);

    cout << "The decimal equivalents of all numbers are \n";

    cout << a << endl
         << b << endl
         << c << endl
         << d;
    return 0;
}
```

**Output:** 

```cpp
The decimal equivalents of all numbers are 
100
171
83
10
```