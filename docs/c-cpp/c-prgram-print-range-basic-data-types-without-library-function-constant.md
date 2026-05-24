# 如何在 C 语言中打印没有任何库函数和常量的基础数据类型范围？

> 原文:[https://www . geesforgeks . org/c-pr gram-print-range-basic-data-type-不带库-function-constant/](https://www.geeksforgeeks.org/c-prgram-print-range-basic-data-types-without-library-function-constant/)

如何编写 C 代码来打印 int、char、short int、unsigned int、unsigned char 等一系列基本数据类型？
假设有符号数以 2 的补码形式存储。
**强烈建议尽量减少浏览器，先自己试试这个。**

以下是**无符号数据类型**应遵循的步骤。
1)使用 sizeof 运算符查找给定数据类型的字节数。
2)通过将 sizeof 的结果乘以 8 找到位数。
3)无符号类型的最小值总是 0，与数据类型无关。
4)无符号类型的最大值是(1<<n–1，其中 n 是数据类型所需的位数。例如，对于通常需要 8 位的 char，最大值为 255。

以下是**签名数据类型**应遵循的步骤。
1)使用 sizeof 运算符查找给定数据类型的字节数。
2)通过将 sizeof 的结果乘以 8 找到位数。
3)有符号类型的最小值为-(1 < < (n-1))。例如，对于通常需要 8 位的 char，最小值为-128。
4)数据类型的最大值为(1<<(n-1))–1，其中 n 是数据类型所需的位数。例如，对于通常需要 8 位的 char，最大值为 127。
下面是 C 代码来演示上述思想。

## C

```cpp
// C program to print range of basic data types
#include <stdio.h>

// Prints min and max value for a signed type
void printUnsignedRange(size_t bytes)
{
    int bits = 8*bytes;

    // Note that the value of 'to' is "(1 << bits) - 1"
    // Writing it in following way doesn't cause overflow
    unsigned int to = ((1 << (bits-1)) - 1) + (1 << (bits-1)) ;

    printf(" range is from %u to %u \n", 0, to);
}

// Prints min and max value for an unsigned type
void printSignedRange(size_t bytes)
{
   int bits = 8*bytes;
   int from = -(1 << (bits-1));
   int to =  (1 << (bits-1)) - 1;
   printf(" range is from %d to %d\n", from, to);
}

int main()
{
    printf("signed char: ");
    printSignedRange(sizeof(char));

    printf("unsigned char: ");
    printUnsignedRange(sizeof(unsigned char));

    printf("signed int: ");
    printSignedRange(sizeof(int));

    printf("unsigned int: ");
    printUnsignedRange(sizeof(unsigned int));

    printf("signed short int: ");
    printSignedRange(sizeof(short int));

    printf("unsigned short int: ");
    printUnsignedRange(sizeof(unsigned short int));

    return 0;
}
```

## C++

```cpp
#include <iostream>                /*1ULL is used to tell compiler use 1 which is having data type unsigned long long*/
using namespace std;            /*if we use 1 only it will be explained as 1 of data type int which will further */
                                /*give us a wrong output by giving a warning: left shift count >= width of type [-Wshift-count-overflow]*/
int main() {

    cout<<"signed char: the range is from "<<(1 << ((sizeof(char)*8)))<<" to "<< ~(1 << ((sizeof(char)*8)-1));

    cout<<"\nunsigned char: the range is from "<<0<<" to "<< ~((1 << ((sizeof(char)*8)-1))+(1 << (sizeof(char)*8)));

    cout<<"\nsigned int: the range is from "<<(1ULL << ((unsigned long long)(sizeof(int)*8)))<<" to "<< ~(1ULL << ((unsigned long long)(sizeof(int)*8)-1ULL));

    cout<<"\nunsigned int: the range is from "<<0<<" to "<< ~((1ULL << ((unsigned long long)(sizeof(int)*8)-1ULL))+(1ULL << (unsigned long long)(sizeof(int)*8)));

      cout<<"\nsigned float: the range is from "<<(1ULL << ((unsigned long long)(sizeof(float)*8)))<<" to "<< ~(1ULL << ((unsigned long long)(sizeof(float)*8)-1ULL));

    cout<<"\nunsigned float: the range is from "<<0<<" to "<< ~((1ULL << ((unsigned long long)(sizeof(float)*8)-1ULL))+(1ULL << (unsigned long long)(sizeof(float)*8)));

      return 0;
}
```

输出:

```cpp
signed char:  range is from -128 to 127
unsigned char:  range is from 0 to 255
signed int:  range is from -2147483648 to 2147483647
unsigned int:  range is from 0 to 4294967295
signed short int:  range is from -32768 to 32767
unsigned short int:  range is from 0 to 65535
```

请注意，上述函数不能用于 float。此外，上述程序可能不适用于大于 int 的数据类型，如“long long int”。我们可以通过将“to”和“from”的数据类型更改为 long long int 来使其适用于更大的类型。
本文由**阿沛·拉提**供稿。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息