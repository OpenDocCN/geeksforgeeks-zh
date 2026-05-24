# c++ STL 中的无序 _ 映射最大 _ 加载 _ 因子

> 原文:[https://www . geesforgeks . org/unordered _ map-max _ load _ factor-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-max_load_factor-in-c-stl/)

C++ STL 中的**无序 _map::max_load_factor** 是一个内置函数，用于获取和设置无序 _map 中的最大加载因子。负载系数是容器中元素数量与铲斗数量之间的比率。默认情况下，无序映射最大负载系数为 1.0。
**语法:**max _ load _ factor 有两种类型的函数。

> 1.  浮动最大负载系数()
> 2.  void 最大负载系数(浮动新大小)

**返回类型:**只有第一个版本返回 max_load_factor。

**参数:**只有第二版接受新尺寸。

**注:**

*   第一个版本返回最大负载系数。
*   第二个版本设置了新的负载系数。

**例 1**

```cpp
// C++ program to illustrate the
// unordered_map::max_bucket_count function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<char, int> sample;

    // insert elements
    sample.insert({ 'a', 10 });
    sample.insert({ 'b', 10 });
    sample.insert({ 'c', 10 });
    sample.insert({ 'd', 10 });
    sample.insert({ 'e', 10 });
    sample.insert({ 'f', 10 });

    cout << "Current size is :  " << sample.size() << endl;
    cout << "Current load factor is : " << sample.load_factor() << endl;
    cout << "Current Max load factor is " << sample.max_load_factor() << endl;

    // Changing max load factor
    sample.max_load_factor(5.0 / 2.0);
    cout << "Current size is :  " << sample.size() << endl;
    cout << "Current load factor is : " << sample.load_factor() << endl;
    cout << "Current Max load factor is " << sample.max_load_factor() << endl;
    return 0;
}
```

**Output:**

```cpp
Current size is :  6
Current load factor is : 0.857143
Current Max load factor is 1
Current size is :  6
Current load factor is : 0.857143
Current Max load factor is 2.5

```

**例 2**

```cpp
// C++ program to illustrate the
// unordered_map::max_bucket_count function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<int, int> sample;

    // insert elements
    sample.insert({ 1, 10 });
    sample.insert({ 2, 10 });
    sample.insert({ 3, 10 });
    sample.insert({ 4, 10 });

    cout << " Current size is :  " << sample.size() << endl;
    cout << " Current load factor is : " << sample.load_factor() << endl;
    cout << " Current Max load factor is " << sample.max_load_factor() << endl;

    // Changing max load factor
    sample.max_load_factor(5.0 / 2.0);
    cout << " Current size is :  " << sample.size() << endl;
    cout << " Current load factor is : " << sample.load_factor() << endl;
    cout << " Current Max load factor is " << sample.max_load_factor() << endl;
    return 0;
}
```

**Output:**

```cpp
Current size is :  4
 Current load factor is : 0.571429
 Current Max load factor is 1
 Current size is :  4
 Current load factor is : 0.571429
 Current Max load factor is 2.5

```

**复杂度:** O(1)。