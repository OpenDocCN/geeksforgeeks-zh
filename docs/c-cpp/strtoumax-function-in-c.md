# strtoumax()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/strtoumax-function-in-c/](https://www.geeksforgeeks.org/strtoumax-function-in-c/)

C++ 中的 **strtoumax()** 函数将字符串的内容解释为指定基数的整数，并将其值作为 uintmax_t(最大宽度无符号整数)返回。此函数还设置一个指向字符串最后一个有效数字字符后的第一个字符的结束指针，如果没有这样的字符，则指针设置为空。当负数作为字符串输入时，返回值被设置为垃圾值。该功能在 **cinttypes** 头文件中定义。

**语法:**

```cpp
uintmax_t strtoumax(const char* str, char** end, int base)
```

**参数:**该功能接受三个强制参数，如下所述:

*   **字符串:**指定由整数组成字符串。
*   **end:** 指定对 char*类型对象的引用。end 的值由函数设置为字符串中最后一个有效数字字符之后的下一个字符。如果没有使用，这个参数也可以是空指针。
*   **基数:**指定决定字符串中有效字符及其解释的数字基数(基数)

**返回类型:**strtoimax()函数返回两个值，描述如下:

*   如果发生了有效的转换，则该函数将转换后的整数作为整数值返回。
*   如果无法执行有效的转换，并且如果字符串包含减号和相应的整数，则函数返回垃圾值，否则返回零值(0)

以下程序说明了上述功能:

**程序 1 :**

```cpp
// C++ program to illustrate the
// strtoumax() function
#include <iostream>
#include<cinttypes>
#include<cstring>

using namespace std;

// Driver code
int main()
{
    int base = 10;
    char str[] = "999999abcdefg";
    char* end;
    uintmax_t num;

    num = strtoumax(str, &end, base);
    cout << "Given String = " << str << endl;
    cout << "Number with base 10 in string " << num << endl;
    cout << "End String points to " << end << endl
         << endl;

    // in this case the end pointer points to null
    // here base change to char16
    base = 2;
    strcpy(str, "10010");
    cout << "Given String = " << str << endl;
    num = strtoumax(str, &end, base);
    cout << "Number with base 2 in string " << num << endl;
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
Given String = 999999abcdefg
Number with base 10 in string 999999
End String points to abcdefg

Given String = 10010
Number with base 2 in string 18
Null pointer

```

**程序 2 :**

```cpp
// C++ program to illustrate the
// strtoumax() function
#include <iostream>
#include<cinttypes>
#include<cstring>

using namespace std;

// Driver code
int main()
{
    int base = 10;
    char str[] = "-10000";
    char* end;
    uintmax_t num;
    // if negative value is converted then it gives garbage value
    num = strtoumax(str, &end, base);
    cout << "Given String = " << str << endl;
    cout << "Garbage value stored in num " << num << endl;
    if (*end) {
        cout << "End String points to " << end;
    }
    else {
        cout << "Null pointer" << endl
             << endl;
    }

    // in this case no numeric character is there
    // so the function returns 0
    base = 10;
    strcpy(str, "abcd");
    cout << "Given String = " << str << endl;
    num = strtoumax(str, &end, base);
    cout << "Number with base 10 in string " << num << endl;
    if (*end) {
        cout << "End String points to " << end;
    }
    else {
        cout << "Null pointer";
    }
    return 0;
}
```

**Output:**

```cpp
Given String = -10000
Garbage value stored in num 18446744073709541616
Null pointer

Given String = abcd
Number with base 10 in string 0
End String points to abcd

```