# c++ STL 中的无序 _ 多 map max_load_factor()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-max _ load _ factor-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-max_load_factor-function-in-c-stl/)

**无序 _ 多映射::max_load_factor()** 是 C++ STL 中的内置函数，返回无序 _ 多映射容器的最大[加载因子](https://www.geeksforgeeks.org/unordered_multimap-load_factor-function-in-c-stl/)。该功能还提供了设置最大[负载系数](https://www.geeksforgeeks.org/unordered_multimap-load_factor-function-in-c-stl/)的选项。

*   **Syntax** (return maximum load factor):

```cpp
*unordered_multimap_name*.max_load_factor()

```

**参数:**函数不接受任何参数。

**返回值:**返回表示集装箱最大装载系数的整数值。

以下程序说明了上述功能:

**程序 1:**

## c++

```cpp
// C++ program to illustrate the
// unordered_multimap::max_load_factor()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample1;

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    // prints the max load factor
    cout << "The max load factor  of sample1: "
         << sample1.max_load_factor();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**输出:**

```cpp
The max load factor  of sample1: 1
Key and Elements of Sample1 are:{50, 500} {10, 100}

```

*   **Syntax** (set maximum load factor):

```cpp
*unordered_multimap_name*.max_load_factor(N)

```

**参数:**该函数接受单个强制参数 N，该参数指定要设置的负载系数。这个 N 将是集装箱的最大负载系数。

**返回值:**函数不返回任何内容。

下面的程序说明了上面的功能:

T3】c++ T5

```cpp
// C++ program to illustrate the
// unordered_multimap::max_load_factor(N)
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample1;

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    cout << "The max load factor of elements of sample1: "
         << sample1.max_load_factor();

    // sets the load factor
    sample1.max_load_factor(100);

    cout << "\nThe max load factor of sample1 after setting it: "
         << sample1.max_load_factor();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

T6T8**输出:**T1

T12