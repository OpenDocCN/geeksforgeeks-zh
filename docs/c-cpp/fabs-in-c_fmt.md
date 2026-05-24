# C++ 中的 fabs()

> 原文: [https://www.geeksforgeeks.org/fabs-in-c/](https://www.geeksforgeeks.org/fabs-in-c/)

`fabs()` 函数返回参数的绝对值。
数学上表示为 `|a|`。如果参数中给定了值。

## 语法

```cpp
double fabs(double a);
float fabs(float a);
int fabs(int a);
```

## 参数

`fabs()` 函数接受单个参数 `a`，需要返回其绝对值。

## 返回

`fabs()` 函数返回参数的绝对值。

## 错误

两个参数都必须给出，否则会给出错误。
调用 `fabs()` 没有匹配函数，如下所示。

## 代码 1

```cpp
// CPP code to illustrate
// fabs() function
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int a = -10, answer;

    answer = fabs(a);
    cout << "fabs of " << a
         << " is " << answer << endl;

    return 0;
}
```

### 输出

```cpp
fabs of -10 is 10
```

## 代码 2

```cpp
// CPP code to illustrate
// fabs() function
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    long int a = -35;
    double answer;

    answer = fabs(a);
    cout << "fabs of " << a << " is "
         << answer << endl;

    return 0;
}
```

### 输出

```cpp
fabs of -35 is 35
```