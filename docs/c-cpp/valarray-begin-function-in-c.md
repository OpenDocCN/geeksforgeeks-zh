# c++ 中 valarray begin()函数

> 原文:[https://www.geeksforgeeks.org/valarray-begin-function-in-c/](https://www.geeksforgeeks.org/valarray-begin-function-in-c/)

**begin()** 函数在 **valarray** 头文件中定义。这个函数返回一个迭代器，指向 valarray v 中的第一个元素。

**语法:**

```cpp
template< class T > 
    begin( valarray<T>& v );

```

**参数:**该函数取一个代表 valarray 对象的强制参数 **v** 。

**返回:**这个函数将迭代器返回到 valarray 中的第一个值。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of begin() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 10, 20, 30, 40, 50 };

    cout << "valarray contains=";

    for (auto i = begin(varr); i != end(varr); i++) {
        cout << ' ' << *i;
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
valarray contains= 10 20 30 40 50

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of begin() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { -10, -20, -30, -40 };

    cout << "valarray contains=";

    for (auto i = begin(varr); i != end(varr); i++) {
        cout << ' ' << *i;
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
valarray contains= -10 -20 -30 -40

```