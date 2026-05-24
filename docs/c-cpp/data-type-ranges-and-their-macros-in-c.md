# c++ 中的数据类型范围及其宏

> 原文:[https://www . geesforgeks . org/data-type-ranges-and-thes-macros-in-c/](https://www.geeksforgeeks.org/data-type-ranges-and-their-macros-in-c/)

大多数情况下，在竞争性编程中，需要分配变量，即数据类型可以容纳的最大值或最小值，但是记住如此大而精确的数字是一项困难的工作。因此，C++ 有某些宏来表示这些数字，这样就可以直接将这些数字赋给变量，而无需实际键入整数。下面列出了其中的一些。

```cpp
Data Type                              Range                      Macro for min value           Macro for max value
char                                -128 to +127                        CHAR_MIN                      CHAR_MAX
short char                          -128 to +127                       SCHAR_MIN                     SCHAR_MAX
unsigned char                         0  to 255                             0                        UCHAR_MAX

short int                         -32768 to +32767                      SHRT_MIN                      SHRT_MAX
unsigned short int                    0  to  65535                          0                        USHRT_MAX 
int                          -2147483648 to +2147483647                  INT_MIN                       INT_MAX
unsigned int                          0  to  4294967295                     0                         UINT_MAX
long int            -9223372036854775808 to +9223372036854775807        LONG_MIN                      LONG_MAX
unsigned long int                     0  to  18446744073709551615           0                        ULONG_MAX 
long long int       -9223372036854775808 to +9223372036854775807       LLONG_MIN                     LLONG_MAX
unsigned long long int                0  to  18446744073709551615           0                       ULLONG_MAX

float                        1.17549e-38 to  3.40282e+38                 FLT_MIN                       FLT_MAX
float(negative)             -1.17549e-38 to -3.40282e+38                -FLT_MIN                      -FLT_MAX
double                      2.22507e-308 to  1.79769e+308                DBL_MIN                       DBL_MAX
double(negative)           -2.22507e-308 to -1.79769e+308               -DBL_MIN                      -DBL_MAX

```

```cpp
// C++ code to demonstrate the macros for data types
#include<iostream>
#include<limits.h> // for int,char macros
#include<float.h> // for float,double macros
using namespace std;
int main()
{

// Displaying ranges with the help of macros
cout << "char ranges from : " << CHAR_MIN << " to " << CHAR_MAX;
cout << "\n\nshort char ranges from : " << SCHAR_MIN << " to " << SCHAR_MAX;
cout << "\n\nunsigned char ranges from : " << 0 << " to " << UCHAR_MAX;

cout << "\n\n\nshort int ranges from : " << SHRT_MIN << " to " << SHRT_MAX;
cout << "\n\nunsigned short int ranges from : " << 0 << " to " << USHRT_MAX;
cout << "\n\nint ranges from : " << INT_MIN << " to " << INT_MAX;
cout << "\n\nunsigned int ranges from : " << 0 << " to " << UINT_MAX;
cout << "\n\nlong int ranges from : " << LONG_MIN << " to " << LONG_MAX;
cout << "\n\nunsigned long int ranges from : " << 0 << " to " << ULONG_MAX;
cout << "\n\nlong long int ranges from : " << LLONG_MIN << " to " << LLONG_MAX;
cout << "\n\nunsigned long long int ranges from : " << 0 << " to " << ULLONG_MAX;

cout << "\n\n\nfloat ranges from : " << FLT_MIN << " to " << FLT_MAX;
cout << "\n\nnegative float ranges from : " << -FLT_MIN << " to " << -FLT_MAX;
cout << "\n\ndouble ranges from : " << DBL_MIN << " to " << DBL_MAX;
cout << "\n\nnegative double ranges from : " << -DBL_MIN << " to " << +DBL_MAX;

return 0;

}
```

输出:

```cpp
char ranges from : -128 to 127

short char ranges from : -128 to 127

unsigned char ranges from : 0 to 255

short int ranges from : -32768 to 32767

unsigned short int ranges from : 0 to 65535

int ranges from : -2147483648 to 2147483647

unsigned int ranges from : 0 to 4294967295

long int ranges from : -9223372036854775808 to 9223372036854775807

unsigned long int ranges from : 0 to 18446744073709551615

long long int ranges from : -9223372036854775808 to 9223372036854775807

unsigned long long int ranges from : 0 to 18446744073709551615

float ranges from : 1.17549e-38 to 3.40282e+38

negative float ranges from : -1.17549e-38 to -3.40282e+38

double ranges from : 2.22507e-308 to 1.79769e+308

negative double ranges from : -2.22507e-308 to 1.79769e+308

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。