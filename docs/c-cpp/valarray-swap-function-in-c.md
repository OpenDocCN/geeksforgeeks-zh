# c++ 中的 valarray swap()函数

> 原文:[https://www.geeksforgeeks.org/valarray-swap-function-in-c/](https://www.geeksforgeeks.org/valarray-swap-function-in-c/)

**交换()**功能在 **[valarray](https://www.geeksforgeeks.org/std-valarray-class-c/)** 头文件中定义。此函数用于将一个 valarray 的内容与另一个 valarray 交换。

**语法:**

```cpp
void swap( valarray& valarray2 );
```

**参数:**这个方法接受一个参数 **valarray2** ，这个参数代表另一个 valarray，我们必须用它来交换旧的 valarray。

**返回:**这个函数不返回任何东西。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of swap() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing 1st valarray
    valarray<int> varr1 = { 12, 24, 36, 48 };

    // Initializing 2nd valarray
    valarray<int> varr2 = { 20, 40, 60, 80 };

    varr1.swap(varr2);

    // Displaying valarrays after swapping
    cout << "The contents of 1st valarray "
            "after swapping are : ";

    for (int& x : varr1)
        cout << x << " ";

    cout << endl;

    cout << "The contents of 2nd valarray "
            "after swapping are : ";

    for (int& x : varr2)
        cout << x << " ";

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The contents of 1st valarray after swapping are : 20 40 60 80 
The contents of 2nd valarray after swapping are : 12 24 36 48

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of swap() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing 1st valarray
    valarray<int> varr1 = { -12, -24, -36, -48 };

    // Initializing 2nd valarray
    valarray<int> varr2 = { 20, 40, 60, 80 };

    varr1.swap(varr2);

    // Displaying valarrays after swapping
    cout << "The contents of 1st valarray "
            "after swapping are : ";

    for (int& x : varr1)
        cout << x << " ";

    cout << endl;

    cout << "The contents of 2nd valarray "
            "after swapping are : ";

    for (int& x : varr2)
        cout << x << " ";

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The contents of 1st valarray after swapping are : 20 40 60 80 
The contents of 2nd valarray after swapping are : -12 -24 -36 -48

```