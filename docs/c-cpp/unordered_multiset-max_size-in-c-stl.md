# c++ STL 中无序 _ 多集最大 _ 大小

> 原文:[https://www . geesforgeks . org/unordered _ multist-max _ size-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-max_size-in-c-stl/)

**无序 _ 多集**的 **max_size()** 取**无序 _ 多集**容器因系统原因所能容纳的最大元素数，或者取受控序列的最大大小。

**语法:**

```cpp
size_type max_size() const;
```

其中 **size_type** 为无符号整型。

**返回:**成员函数返回对象可以容纳的**最长序列**的长度。总之，*元素的最大数量。*

下面的程序说明了**无序多集最大大小**函数:-

**例 1:**

```cpp
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    // Define the unordered_set
    unordered_multiset<int> num{ 1, 2, 3, 4, 5, 6 };

    cout << "Maximum size = "
         << num.max_size() << "\n";

    cout << "Current size = "
         << num.size();

    return 0;
}
```

**Output:**

```cpp
Maximum size = 1152921504606846975
Current size = 6

```

**复杂度:**
执行一个操作需要**常数(O(1))** 的时间复杂度。