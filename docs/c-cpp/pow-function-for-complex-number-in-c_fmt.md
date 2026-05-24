# C++ 中复数的 `pow()` 函数

> 原文: [https://www.geeksforgeeks.org/pow-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/pow-function-for-complex-number-in-c/)

复数的 `pow()` 函数在 `<complex>` 头文件中定义。该功能是 `pow()` 功能的复数版本。这个函数用来计算复数 `x` 的幂次升到 `y` 次方。

## 语法

> `template<class T> complex<T> pow(const complex<T>& x, int y);`
>
> 或者，
> `template<class T> complex<T> pow(const complex<T>& x, const complex<T>& y);`
>
> 或者，
> `template<class T> complex<T> pow(const complex<T>& x, const T& y);`
>
> 或者，
> `template<class T> complex<T> pow(const T& x, const complex<T>& y);`

## 参数

该方法接受两个参数:

*   `x`: 表示基数为复数。
*   `y`: 表示指数为复数值。

## 返回值

此函数返回基数 `x` 的复数幂升至 `y` 次方。

下面的程序说明了 C++ 中的 `pow()` 函数:

## 示例 1

```cpp
// c++ program to demonstrate
// example of pow() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (1.0+2.0i)
    complex<double> complexnumber(1.0, 2.0);

    // use of pow() function for complex number
    cout << "(1.0, 2.0)^2 = "
         << pow(complexnumber, 2)
         << endl;

    return 0;
}
```

**输出:**

```cpp
(1.0, 2.0)^2 = (-3,4)
```

## 示例 2

```cpp
// c++ program to demonstrate
// example of pow() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (2.0+1.0i)
    complex<double> complexnumber(2.0, 1.0);

    // use of pow() function for complex number
    cout << "(2.0, 1.0)^3 = "
         << pow(complexnumber, 3)
         << endl;

    return 0;
}
```

**输出:**

```cpp
(2.0, 1.0)^3 = (2,11)
```