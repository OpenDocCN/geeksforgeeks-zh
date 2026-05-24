# strtoimax()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/strtoimax-function-in-c/](https://www.geeksforgeeks.org/strtoimax-function-in-c/)

C++ 中的 **strtoimax()** 函数将字符串的内容解释为指定基数的整数，并将其值返回为 intmax_t(最大宽度整数)。此函数还设置一个指向字符串最后一个有效数字字符后的第一个字符的结束指针，如果没有这样的字符，则指针设置为空。该功能在 **cinttypes** 头文件中定义。
**语法:**

```cpp
intmax_t strtoimax(const char* str, char** end, int base)
```

**参数:**

*   **字符串**:指定由整数组成字符串。
*   **end** :是对 char*类型对象的引用。end 的值由函数设置为字符串中最后一个有效数字字符之后的下一个字符。如果没有使用，这个参数也可以是空指针。
*   **碱基:**代表 t

确定字符串中有效字符及其解释的数字基数(基数)
**返回类型<:**strtoimax()函数返回两个值，如下所述:

*   如果发生了有效的转换，则该函数将转换后的整数作为整数值返回。
*   如果无法执行有效转换，则返回零值(0)

以下程序说明了上述功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// strtoimax() function
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    int base = 10;
    char str[] = "1000xyz";
    char* end;
    intmax_t num;

    num = strtoimax(str, &end, base);
    cout << "Given String = " << str << endl;
    cout << "Number with base 10 in string " << num << endl;
    cout << "End String points to " << end << endl
         << endl;

    // in this case the end pointer points to null
    // here base change to char16
    base = 16;
    strcpy(str, "ff");
    cout << "Given String = " << str << endl;
    num = strtoimax(str, &end, base);
    cout << "Number with base 16 in string " << num << endl;
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
Given String = 1000xyz
Number with base 10 in string 1000
End String points to xyz

Given String = ff
Number with base 16 in string 255
Null pointer
```

**程序 2:**
程序转换不同基数的多个数值

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// strtoimax() function
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    char str[] = "10 50 f 100 ";
    char* end;
    intmax_t a, b, c, d;

    // at base 10
    a = strtoimax(str, &end, 10);
    // at base 8
    b = strtoimax(end, &end, 8);
    // at base 16
    c = strtoimax(end, &end, 16);
    // at base 2
    d = strtoimax(end, &end, 2);
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
10
40
15
4
```