# c++ 中的用户定义文字

> 原文:[https://www.geeksforgeeks.org/user-defined-literals-cpp/](https://www.geeksforgeeks.org/user-defined-literals-cpp/)

**U** ser **D** 定义的**L**ITER(**UDL**)是从 C++ 11 用 C++ 添加的。尽管 C++ 为各种内置类型提供了文本，但这些类型是有限的。

**内置类型的文字示例:**

```cpp
// Examples of classical literals for built-in types.
42    // int
2.4    // double
3.2F    // float
'w'    // char
32ULL    // Unsigned long long
0xD0    // Hexadecimal unsigned
"cd"    // C-style string(const char[3]")
```

**我们为什么要用 UDLs？**
让我们考虑下面的例子来理解 UDLs 的需求。

```cpp
long double Weight = 2.3; //  pounds? kilograms? grams?

// With UDL, we attach units to the values which has
// following advantages
// 1) The code becomes readable.
// 2) Conversion computations are done at compile time. 
weight = 2.3kg;
ratio = 2.3kg/1.2lb;
```

为了计算上述比率，有必要将它们转换为相同的单位。 **UDLs** 帮助我们克服单位翻译成本。我们可以为用户定义的类型定义用户定义的文字，为内置类型定义新形式的文字。它们有助于提高代码中常量的可读性。编译器在编译时用代码中定义的实际值替换 **UDLs** 的值。 **UDL 的**没有节省太多的编码时间，但是越来越多的计算可以转移到编译时，以便更快地执行。

**用户定义的文字示例:**

```cpp
"hello"s            // string
4.3i                // imaginary
101000111101001b    // binary
53h                // hours
234093270497230409328432840923849 // extended-precision
```

**udl**被视为对文字运算符的调用。仅支持后缀形式。文字操作符的名称是**操作符" "**，后跟后缀。

**例 1:**

```cpp
// C++ code to demonstrate working of user defined
// literals (UDLs)
#include<iostream>
#include<iomanip>
using namespace std;

// user defined literals

// KiloGram
long double operator"" _kg( long double x )
{
    return x*1000;
}

// Gram
long double operator"" _g( long double x )
{
    return x;
}

// MiliGram
long double operator"" _mg( long double x )
{
    return x / 1000;
}

// Driver code
int main()
{
    long double weight = 3.6_kg;
    cout << weight << endl;
    cout << setprecision(8) << ( weight + 2.3_mg ) << endl;
    cout << ( 32.3_kg / 2.0_g ) << endl;
    cout << ( 32.3_mg *2.0_g ) << endl;
    return 0;
}
```

**Output:**

```cpp
3600
3600.0023
16150
0.0646

```

**例 2:**

```cpp
#include <iostream>
#include <complex>
using namespace std;

// imaginary literal
constexpr complex <double> operator"" _i( long double d )
{
    return complex <double> { 0.0 , static_cast <double> ( d ) };
}

int main()
{
    complex <double> z = 3.0 + 4.0_i;
    complex <double> y = 2.3 + 5.0_i;
    cout << "z + y = " << z+y << endl;
    cout << "z * y = " << z*y << endl;
    cout << "abs(z) = " << abs(z) << endl;
    return 0;
}
```

**Output:**

```cpp
z + y = (5.3,9)
z * y = (-13.1,24.2)
abs(z) = 5

```

这里， [constexpr](https://www.geeksforgeeks.org/understanding-constexper-specifier-in-c/) 用于启用编译时评估。

**限制:**
UDL 只能使用以下参数:

```cpp
char const*
unsigned long long
long double
char const*, std::size_t
wchar_t const*, std::size_t
char16_t const*, std::size_t
char32_t const*, std::size_t
```

但是返回值可以是任何类型。

本文由**马希马·瓦什尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。