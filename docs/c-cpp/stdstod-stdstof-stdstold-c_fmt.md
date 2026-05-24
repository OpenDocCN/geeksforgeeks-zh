# std::stod，std::stof，std::stold 在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdstod-stdstof-stdstold-c/](https://www.geeksforgeeks.org/stdstod-stdstof-stdstold-c/)

## 1. `std::stod()`
它将字符串转换为双精度浮点数。
语法：

```cpp
double stod( const std::string& str, std::size_t* pos = 0 );
double stod( const std::wstring& str, std::size_t* pos = 0 );
```

返回值：返回一个 `double` 类型的值。
参数：
- `str`：要转换的字符串。
- `pos`：一个整数的地址，用于存储已处理的字符数。此参数也可以是一个空指针，在这种情况下它不会被使用。

```cpp
// CPP program to illustrate
// std::stod()
#include <string>
#include <iostream>

int main(void)
{
    std::string str = "y=4.4786754x+5.6";

    double y, x, a, b;
    y = 0;
    x = 0;

    // offset will be set to the length of
    // characters of the "value" - 1.
    std::size_t offset = 0;

    a = std::stod(&str[2], &offset);
    b = std::stod(&str[offset + 3]);

    std::cout << b;
    return 0;
}
```

输出：

```cpp
5.6
```

**另一个例子:**

```cpp
// CPP program to illustrate
// std::stod()
#include <iostream>
#include <string>
using namespace std;
int main()
{
    string b = "5";
    double a = stod(b);
    int c = stoi(b);
    cout << b << " " << a << " " << c << endl;
}
```

输出：

```cpp
5 5 5
```

如果不执行转换，将引发 `invalid_argument` 异常。如果读取的值超出了双精度值可表示的范围，则会引发超出范围异常。无效的 `idx` 会导致未定义的行为。

## 2. `std::stof`
它将字符串转换为单精度浮点数。
语法：

```cpp
float stof( const string& str, size_t* pos = 0 );
float stof( const wstring& str, size_t* pos = 0 );
```

参数：
- `str`：要转换的字符串。
- `pos`：一个整数的地址，用于存储已处理的字符数。此参数也可以是一个空指针，在这种情况下它不会被使用。
返回值：它返回一个 `float` 类型的值。

**例 1:**

```cpp
// CPP program to illustrate
// std::stof()
#include <iostream>
#include <string>
int main()
{
    std::string x;
    x = "20";
    float y = std::stof(x) + 2.5;
    std::cout << y;
    return 0;
}
```

输出：

```cpp
22.5
```

**例 2:**

```cpp
// CPP program to illustrate
// std::stof()
#include <iostream>
#include <string>
int main()
{
    std::string str = "5000.5";
    float x = std::stof(str);
    std::cout << x;
    return 0;
}
```

**输出:**

```cpp
5000.5
```

如果无法执行转换，将引发无效的参数异常。

## 3. `std::stold`
它将字符串转换为长双精度浮点数。
语法：

```cpp
long double stold( const string& str, size_t *pos = 0 );
long double stold (const wstring& str, size_t* pos = 0);
```

参数：
- `str`：要转换的字符串。
- `pos`：一个整数的地址，用于存储第一个未转换字符的索引。此参数也可以是一个空指针，在这种情况下它不会被使用。
返回值：它返回一个 `long double` 类型的值。

**实施例 1:**

```cpp
// CPP program to illustrate
// std::stold()
#include <iostream>
#include <string>
int main()
{
    std::string str = "500087";
    long double x = std::stold(str);
    std::cout << x;
    return 0;
}
```

输出：

```cpp
500087
```

**例 2:**

```cpp
// CPP program to illustrate
// std::stold()
#include <iostream>
#include <string>
int main()
{
    std::string x;
    x = "2075";
    long double y = std::stof(x) + 2.5;
    std::cout << y;
    return 0;
}
```

输出：

```cpp
2077.5
```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。