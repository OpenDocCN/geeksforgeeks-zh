# 在 C++ 中交换()

> 原文:[https://www.geeksforgeeks.org/swap-in-cpp/](https://www.geeksforgeeks.org/swap-in-cpp/)

函数 **std::swap()** 是 C++ 标准模板库(STL)中的一个内置函数，用于交换两个变量的值。

**语法:**

```cpp
swap(a, b)

```

**参数:**函数接受两个需要交换的强制参数 a 和 b。参数可以是任何数据类型。

**返回值:**函数不返回任何东西，它交换两个变量的值。

下面的程序说明了 swap()函数:

**程序 1:**

```cpp
// C++ program for illustration of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int a = 10;
    int b = 20;
    cout << "Value of a before: " << a << endl;
    cout << "Value of b before: " << b << endl;

    // swap values of the variables
    swap(a, b);
    cout << "Value of a now: " << a << endl;
    cout << "Value of b now: " << b << endl;
    return 0;
}
```

**Output:**

```cpp
Value of a before: 10
Value of b before: 20
Value of a now: 20
Value of b now: 10

```

**程序 2:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string a = "Geeks";
    string b = "function";
    cout << "Value of a before: " << a << endl;
    cout << "Value of b before: " << b << endl;
    swap(a, b);
    cout << "Value of a now: " << a << endl;
    cout << "Value of b now: " << b << endl;
    return 0;
}
```

**Output:**

```cpp
Value of a before: Geeks
Value of b before: function
Value of a now: function
Value of b now: Geeks

```