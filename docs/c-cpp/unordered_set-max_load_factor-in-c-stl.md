# c++ STL 中的无序 _ 设置 max_load_factor()

> 原文:[https://www . geesforgeks . org/unordered _ set-max _ load _ factor-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-max_load_factor-in-c-stl/)

**无序集::max_load_factor()** 是 C++ STL 中的一个函数，返回(或设置)无序集容器的当前最大加载因子。

负载系数是容器中元素的数量与桶的数量(桶计数)之间的比率。默认情况下，无序集容器的最大负载系数设置为 1.0。

### 最大负载系数()

**语法**:

```cpp
unordered_set_name.max_load_factor()
```

**返回值**该方法返回当前最大负载系数。

下面的程序说明了无序 _ 集合::max_load_factor()方法:

```cpp
// C++ program o illustrate the
// unordered_set::max_load_factor() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_set<int> uset = { 1, 5, 4, 7 };

    // Get the max_load_factor of uset
    cout << "Maximum load factor of uset: "
         << uset.max_load_factor()
         << endl;

    // Now check the current load factor
    cout << "Current load factor of uset: "
         << uset.load_factor();
}
```

**Output:**

```cpp
Maximum load factor of uset: 1
Current load factor of uset: 0.8

```

### 最大负载系数(浮动)

**语法**

```cpp
unordered_set_name.max_load_factor(float z)
```

**参数:**该方法以一个**浮点数**为参数，设置最大加载因子。

**返回值:**此方法不返回值。

下面的程序说明了无序 _ 集合::最大 _ 加载 _ 因子(浮点)方法:

```cpp
// C++ program to illustrate the
// unordered_set::max_load_factor() function

#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    unordered_set<int> uset = { 1, 5, 4, 7 };

    // Now set the max_load_factor as  0.5
    uset.max_load_factor(0.5);

    // Now get the new max_load_factor of uset
    cout << "New Maximum load factor of uset: "
         << uset.max_load_factor()
         << endl;

    // Check the new load factor
    cout << "Current load factor of uset1: "
         << uset.load_factor()
         << endl;
}
```

**Output:**

```cpp
New Maximum load factor of uset: 0.5
Current load factor of uset1: 0.363636

```