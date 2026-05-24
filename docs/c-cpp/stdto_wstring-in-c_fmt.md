# C++ 中的 std::to_wstring

> 原文: [https://www.geeksforgeeks.org/stdto_wstring-in-c/](https://www.geeksforgeeks.org/stdto_wstring-in-c/)

此函数用于将数值转换为宽字符串。它将 `int`、`long long`、`float`、`double` 等数据类型的数值解析为宽字符串。它返回一个 `wstring` 类型的宽字符串，表示传递给函数的数值。在函数内部，数据类型被转换为 `wstring`，并将数值作为其参数传递，最终返回一个包含已转换数值的 `wstring` 类型字符串。

## 语法

```cpp
wstring to_wstring (int val);
wstring to_wstring (long long val);
wstring to_wstring (float val);
wstring to_wstring (double val);
```

**参数：**
`val`：要转换为宽字符串的数值。

**返回值：**
将传入的数值转换为 `wstring` 类型的宽字符串并返回。

## 示例

```cpp
// C++ code to convert numerical value
// to wide string data type
// using the to_wstring function

// These header files contains wcout,
// wstring and to_wstring
#include <iostream>
#include <string>
using namespace std;

//Driver code
int main ()
{

// Data types to be typecasted
float x = 3.1415926;
int a = 5 , b = 9;
double y = 6.29;

// numerical values being typecasted into wstring
wstring pi = L"Pi is " + to_wstring(x);
wstring perfect = to_wstring(a+b) +
                    L" is a number";
wstring num = to_wstring(y/x) +
                    L"is division of two numbers";

// Printing the typecasted wstring
wcout << pi << L'\n';
wcout << perfect << L'\n';
wcout << num <<L'\n';
return 0;
}
```

**输出：**

```cpp
Pi is 3.141593
14 is a number
2.002169is division of two numbers
```

## 应用

可用于平均值等报表语句中使用的计算，因此我们无需为此编写任何额外的类型转换语句，可以直接使用该函数转换数值。

示例：假设一个部门的 HOD 正在为他的部门中的多个部门提交报告，并且他必须避免数据类型转换，以便他可以使用 `to_wstring` 函数来完成这个特定的任务。

下面是实现：

```cpp
// These header files contains wcout and wstring
#include <iostream>
#include <string>

using namespace std;

// Driver code
int main ()
{

// Data types to be typecasted
int a = 600 , b = 150;

// numerical values being typecasted into wstring
wstring rep = L"Number of section = " + to_wstring(a/b);
wstring sec_rep = to_wstring(b) +
            L" is the number of students in each section";

// Printing the typecasted wstring
wcout << rep << L'\n';
wcout << sec_rep << L'\n';
return 0;
}
```

**输出：**

```cpp
Number of section =  4
150 is the number of students in each section
```

在上面的例子中，我们不需要每次都对数据类型进行手动类型转换，但是在这个函数的帮助下，避免了外部类型转换，这对系统是有利的，因为外部类型转换比 STL 函数花费更多的时间。