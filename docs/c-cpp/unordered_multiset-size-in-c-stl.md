# c++ STL 中的无序 _ 多集大小()

> 原文:[https://www . geesforgeks . org/unordered _ multist-size-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-size-in-c-stl/)

**无序 _ 多集**的 **size()** 方法用来统计调用它的无序 _ 集合的元素个数。它获取容器中元素的数量，并计算元素的数量。

**语法:**

```cpp
size_type size() const;
```

其中 **size_type** 为无符号整型。

**返回值:**该函数返回受控序列的长度，或者简单地说，它返回*容器中元素的数量*。

下面的程序说明了**无序 _ 多集大小()**函数:-

**示例:**

```cpp
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    // Define the unordered_set
    unordered_multiset<int> numbers{ 1, 2, 3, 4, 5, 6 };

    // Calculate and print
    // the size of the unordered_multiset
    cout << "The container has "
         << numbers.size()
         << " elements in it";
}
```

**Output:**

```cpp
The container has 6 elements in it

```

**复杂度:**
执行一个操作需要**常数(O(1))** 的时间复杂度。