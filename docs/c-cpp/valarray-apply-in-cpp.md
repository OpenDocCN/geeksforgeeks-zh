# valarray 在 C++ 中应用()

> 原文:[https://www.geeksforgeeks.org/valarray-apply-in-cpp/](https://www.geeksforgeeks.org/valarray-apply-in-cpp/)

**apply()** 功能在 **[valarray](https://www.geeksforgeeks.org/std-valarray-class-c/)** 头文件中定义。这个函数返回一个 valarray，它的每个元素都被初始化为将 func 应用于它在*this 中的对应元素的结果。

**语法:**

```cpp
valarray apply (T func(T)) const;
valarray apply (T func(const T&)) const;

```

**参数:**这个方法接受一个强制参数**函数**，它代表一个指向带有类型为 T 的参数的函数的指针

**返回值:**该方法返回一个**数组**对象，其结果是将**函数**应用于*的所有元素。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of apply() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<int> varr = { 15, 10, 30, 33, 40 };

    // Declaring new valarray
    valarray<int> varr1;

    // Using apply() to increment all elements by 5
    varr1 = varr.apply([](int x) { return x = x + 5; });

    // Displaying new elements value
    cout << "The new valarray "
         << "with manipulated values is : ";

    for (int& x : varr1)
        cout << x << " ";

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 20 15 35 38 45

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of apply() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<int> varr = { 15, 10, 30, 33, 40 };

    // Declaring new valarray
    valarray<int> varr1;

    // Using apply() to decrement all elements by 5
    varr1 = varr.apply([](int x) { return x = x - 5; });

    // Displaying new elements value
    cout << "The new valarray"
         << " with manipulated values is : ";

    for (int& x : varr1)
        cout << x << " ";

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 10 5 25 28 35

```