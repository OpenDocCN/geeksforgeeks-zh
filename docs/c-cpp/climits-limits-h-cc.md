# <climits>(limits.h)在 C/C++ </climits> 中

> 原文:[https://www.geeksforgeeks.org/climits-limits-h-cc/](https://www.geeksforgeeks.org/climits-limits-h-cc/)

整数值的最大值和最小值非常有用，或者简单地说，任何整数类型的极限在编程中都起着相当大的作用。可以使用不同的宏来代替记住这些值。

**<climits>(limits . h)**定义积分类型的大小。
这个头定义了常数，并限制了所用的特定系统和编译器实现的基本整数类型。
基本浮点类型的限制在< cfloat > ( < float.h >中定义。
宽度特定的整数类型和其他类型定义的限制在<CST int>(<stdint . h>)中定义。

不同的宏常数有:

1. **CHAR_MIN :**

```cpp
Minimum value for an object of type char
Value of CHAR_MIN is either -127 (-27+1) or less* or 0
```

2. **CHAR_MAX :**

```cpp
Maximum value for an object of type char
Value of CHAR_MAX is either 127 (27-1) or 255 (28-1) or greater*    
```

3. **SHRT_MIN :**

```cpp
Minimum value for an object of type short int
Value of SHRT_MIN is -32767 (-215+1) or less*
```

4. **SHRT_MAX :**

```cpp
Maximum value for an object of type short int
Value of SHRT_MAX is 32767 (215-1) or greater*
```

5. **USHRT_MAX :**

```cpp
Maximum value for an object of type unsigned short int    
Value of USHRT_MAX is 65535 (216-1) or greater*
```

6. **INT_MIN :**

```cpp
Minimum value for an object of type int    
Value of INT_MIN is -32767 (-215+1) or less*
```

7. **INT_MAX :**

```cpp
Maximum value for an object of type int    
Value of INT_MAX is 32767 (215-1) or greater*
```

8.uint _ max:

```cpp
Maximum value for an object of type unsigned int    
Value of UINT_MAX is 65535 (216-1) or greater*
```

9. **LONG_MIN :**

```cpp
Minimum value for an object of type long int    
Value of LONG_MIN is -2147483647 (-231+1) or less*
```

10. **LONG_MAX :**

```cpp
Maximum value for an object of type long int    
Value of LONG_MAX is 2147483647 (231-1) or greater*
```

11. **ULONG_MAX :**

```cpp
Maximum value for an object of type unsigned long int    
Value of ULONG_MAX is 4294967295 (232-1) or greater*
```

12\. **LLONG_MIN ：**

```cpp
Minimum value for an object of type long long int    
Value of LLONG_MIN is -9223372036854775807 (-263+1) or less*
```

13\. **LLONG_MAX ：**

```cpp
Maximum value for an object of type long long int    
Value of LLONG_MAX is 9223372036854775807 (263-1) or greater*
```

14. **ULLONG_MAX :**

```cpp
Maximum value for an object of type unsigned long long int    
Value of ULLONG_MAX is 18446744073709551615 (264-1) or greater*
```

注**实际值取决于特定的系统和库实现，但应反映目标平台中这些类型的限制。
您的机器的值可能取决于它是 32 位机器还是 64 位机器。

**兼容性:**
LLONG_MIN、LLONG_MAX 和 ULLONG_MAX 是为符合 1999 年或更高版本 C 标准(自 2011 年起仅包括 C++ 标准:C++ 11)的库定义的。
这些宏的两个应用是检查整数溢出和计算非常大或非常小的元素数组中的最小值或最大值。

**下面的程序将显示您机器的相应值:**

## C++

```cpp
// C++ program to demonstrate working of
// constants in climits.
#include <climits>
#include <iostream>

using namespace std;

int main()
{
    cout << "CHAR_MIN : " << CHAR_MIN << endl;
    cout << "CHAR_MAX : " << CHAR_MAX << endl;
    cout << "SHRT_MIN : " << SHRT_MIN << endl;
    cout << "SHRT_MAX : " << SHRT_MAX << endl;
    cout << "USHRT_MAX : " << USHRT_MAX << endl;
    cout << "INT_MIN : " << INT_MIN << endl;
    cout << "INT_MAX : " << INT_MAX << endl;
    cout << "UINT_MAX : " << UINT_MAX << endl;
    cout << "LONG_MIN : " << LONG_MIN << endl;
    cout << "LONG_MAX : " << LONG_MAX << endl;
    cout << "ULONG_MAX : " << ULONG_MAX << endl;
    cout << "LLONG_MIN : " << LLONG_MIN << endl;
    cout << "LLONG_MAX : " << LLONG_MAX << endl;
    cout << "ULLONG_MAX : " << ULLONG_MAX << endl;
    return 0;
}
```

输出(取决于机器):

```cpp
CHAR_MIN : -128
CHAR_MAX : 127
SHRT_MIN : -32768
SHRT_MAX : 32767
USHRT_MAX : 65535
INT_MIN : -2147483648
INT_MAX : 2147483647
UINT_MAX : 4294967295
LONG_MIN : -9223372036854775808
LONG_MAX : 9223372036854775807
ULONG_MAX : 18446744073709551615
LLONG_MIN : -9223372036854775808
LLONG_MAX : 9223372036854775807
ULLONG_MAX : 18446744073709551615
```