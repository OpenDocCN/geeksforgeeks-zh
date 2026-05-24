# ldexp() 在 C++

> 原文: [https://www.geeksforgeeks.org/ldexp-in-cpp/](https://www.geeksforgeeks.org/ldexp-in-cpp/)

`ldexp()` 函数接受两个参数 `a` 和 `b`，并返回 `a` 与 2 的 `b` 次幂的乘积，即 `a * (2^b)`。

## 语法

```cpp
double ldexp (double a, double b);
float ldexp (float a, float b);
long double ldexp (long double a, long double b);
```

## 错误和异常

1.  必须给出这两个参数，否则会给出错误：调用 `ldexp()` 没有匹配的函数。
2.  如果我们将字符串作为参数传递，我们将得到错误：没有匹配的函数来调用 `ldexp(const char[n], const char[n])`。
3.  如果我们将 `std::numeric_limits::max()` 作为两个参数传递，我们将得到 `inf` (infinity) 作为输出。

## 示例

```cpp
Input  : ldexp(5.35, 4)
Output : 85.6

Input  : ldexp(25, 5)
Output : 800
```

### 代码 1

```cpp
// C++ implementation of the
// above function
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    double a = 5.35;
    int b = 4;
    cout << ldexp(a, b);
    return 0;
}
```

**Output:**

```cpp
85.6
```

### 代码 2

```cpp
// CPP implementation of the
// above function
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    int a = 25, b = 5;
    cout << ldexp(a, b);
    return 0;
}
```

**Output:**

```cpp

```