# c++ 中的 valarray resize()函数

> 原文:[https://www . geesforgeks . org/valarray-resize-function-in-c/](https://www.geeksforgeeks.org/valarray-resize-function-in-c/)

**resize()** 功能在 [**valarray**](https://www.geeksforgeeks.org/std-valarray-class-c/) 头文件中定义。该函数调整 valarray 的大小以包含 **n** 个元素，并为每个元素赋值。
**语法:**

```cpp
void resize( size_t n, T value = T() );
```

**参数:**该方法接受两个参数:

*   **n:** 代表 valarray 的新尺寸。
*   **值:**表示初始化新元素的值。

**返回:**这个函数不返回任何东西。
以下程序说明了上述功能:
**示例 1:-**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of resize() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing  valarray
    valarray<int> varr = { 20, 40, 60, 80 };

    varr.resize(2, 3);

    // Displaying valarray after resizes
    cout << "The contents of valarray "
            "after resizes are : ";
    for (int& x : varr)
        cout << x << " ";
    cout << endl;

    return 0;
}
```

**Output:** 

```cpp
The contents of valarray after resizes are : 3 3
```

**实施例 2:-**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of resize() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing  valarray
    valarray<int> varr = { 20, 40, 60, 80 };

    varr.resize(12, 5);

    // Displaying valarray after resizes
    cout << "The contents of valarray "
            "after resizes are : ";
    for (int& x : varr)
        cout << x << " ";
    cout << endl;

    return 0;
}
```

**Output:** 

```cpp
The contents of valarray after resizes are : 5 5 5 5 5 5 5 5 5 5 5 5
```