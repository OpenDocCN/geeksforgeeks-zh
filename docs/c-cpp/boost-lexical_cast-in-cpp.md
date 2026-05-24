# 助推。C++ 中的词法转换

> 原文:[https://www.geeksforgeeks.org/boost-lexical_cast-in-cpp/](https://www.geeksforgeeks.org/boost-lexical_cast-in-cpp/)

助推。在库“boost/词法 _Cast.hpp”中定义的词典 cast 提供了一个转换操作符 boost::词法 _cast，它可以将数字从字符串转换为数字类型，如 int 或 double，反之亦然。

boost::词法 _cast 是类似于 [std::stoi()](https://www.geeksforgeeks.org/stdstod-stdstof-stdstold-c/) 、 [std::stod()](https://www.geeksforgeeks.org/stdstod-stdstof-stdstold-c/) 和 [std::to_string()](https://www.geeksforgeeks.org/stdto_string-in-cpp/) 等函数的替代函数，这些函数在 C++ 11 中被添加到标准库中。
现在让我们看看这个函数在程序中的实现。
 **示例:**

```cpp
Conversion
integer -> string
string- > integer
integer -> char
float- > string

```

**关联异常:**如果转换失败，将引发从 bad_cast 派生的 bad _ 词法 _cast 类型的异常。它引发了一个异常，因为 float 52.50 和字符串“GeeksforGeeks”不能转换为 int 类型的数字。

```cpp
// CPP program to illustrate
// Boost.Lexical_Cast in C++
#include "boost/lexical_cast.hpp"
#include <bits/stdc++.h>
using namespace std;
using boost::lexical_cast;
using boost::bad_lexical_cast;
int main() {

  // integer to string conversion
  int s = 23;
  string s1 = lexical_cast<string>(s);
  cout << s1 << endl;

  // integer to char conversion
  array<char, 64> msg = lexical_cast<array<char, 64>>(45);
  cout << msg[0] << msg[1] << endl;

  // string to integer conversion in integer value
  int num = lexical_cast<int>("1234");
  cout << num << endl;

  // bad conversion float to int
  // using try and catch we display the error
  try {
    int num2 = lexical_cast<int>("52.20");
  }

  // To catch exception
  catch (bad_lexical_cast &e) {
    cout << "Exception caught : " << e.what() << endl;
  }

  // bad conversion string to integer character
  // using tru and catch we display the error
  try {
    int i = lexical_cast<int>("GeeksforGeeks");
  }

  // catching Exception
  catch (bad_lexical_cast &e) {
    cout << "Exception caught :" << e.what() << endl;
  }

  return 0;
}
```

输出:-

```cpp
23
45
1234
Exception caught : bad lexical cast: source type value could not be interpreted as target
Exception caught :bad lexical cast: source type value could not be interpreted as target

```

参考:-[http://www.boost.org/](http://www.boost.org/)