# 用 C++ 计算数据类型的范围

> 原文:[https://www . geesforgeks . org/calculate-range-data-type-using-c/](https://www.geeksforgeeks.org/calculate-range-data-types-using-c/)

C++ 程序，用于打印范围数据类型，如 int、char、short。

**有符号数据类型**

```cpp
METHOD
1.) calculate total number of bits by multiplying sizeof with 8 (say n)
2.) Calculate  -2^(n-1) for minimum range
3.) Calculate  (2^(n-1))-1 for maximum range

```

```cpp
// CPP program to calculate 
// range of signed data type
#include <bits/stdc++.h>
#define SIZE(x) sizeof(x) * 8
using namespace std;

// function to calculate range of
//unsigned data type
void printSignedRange(int count)
{
    int min = pow(2, count - 1);
    int max = pow(2, count - 1) - 1;
    printf("%d to %d", min * (-1), max);
}

// DRIVER program
int main()
{
    cout << "signed char: ";
    printSignedRange(SIZE(char));
    cout << "\nsigned int: ";
    printSignedRange(SIZE(int));
    cout << "\nsigned short int: ";
    printSignedRange(SIZE(short int));

    return 0;
}
```

输出:

```cpp
signed char: -128 to 127
signed int: -2147483648 to 2147483647
signed short int: -32768 to 32767

```

**无符号数据类型**

```cpp
METHOD
1.)Find number of bits by multiplying result of sizeof with 8 say n
2.)minimum range is always zero for unsigned data type
3.)for maximum range calculate 2^n-1

```

```cpp
// CPP program to calculate range 
// of given unsigned data type
#include <bits/stdc++.h>
#define SIZE(x) sizeof(x) * 8
using namespace std;

// function to calculate range 
// of given unsigned data type
void UnsignedRange(int count)
{
    // calculate 2^number of bits
    unsigned int max =  pow(2, count) - 1;

    cout << "0 to " << max;
}

// DRIVER program
int main()
{
    cout << "unsigned char: ";
    UnsignedRange(SIZE(unsigned char));
    cout << "\nunsigned int: ";
    UnsignedRange(SIZE(unsigned int));
    cout << "\nunsigned short int: ";
    UnsignedRange(SIZE(unsigned short));
    return 0;
}
```

输出:

```cpp
unsigned char: 0 to 255
unsigned int: 0 to 4294967295
unsigned short int: 0 to 65535

```