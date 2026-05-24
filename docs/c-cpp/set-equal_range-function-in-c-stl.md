# 在 C++ STL 中设置 equal_range()函数

> 原文:[https://www . geesforgeks . org/set-equal _ range-function-in-c-STL/](https://www.geeksforgeeks.org/set-equal_range-function-in-c-stl/)

**set::equal_range()** 是 C++ STL 中的一个内置函数，它返回一个对的迭代器。该对指的是包含容器中所有元素的范围，这些元素的键等价于 K。由于 set 包含唯一的元素，下限将是元素本身，上限将指向键 K 之后的下一个元素。如果没有元素匹配键 K，则返回的范围长度为 0，根据容器的内部比较对象(key_comp)，两个迭代器都指向大于 K 的第一个元素。如果键超过了集合容器中的最大元素，它将返回一个迭代器，指向集合容器中的最后一个元素。

**语法:**

```cpp
set_name.equal_range(key) 

```

**参数:**该功能接受一个强制参数*键*，该键指定要返回其在设定容器中的范围的键。

**返回值:**函数返回一个对的迭代器。(key_comp)。该对指的是包含容器中所有元素的范围，这些元素的键等价于 K。由于 set 包含唯一的元素，下限将是元素本身，上限将指向键 K 之后的下一个元素。如果没有元素匹配键 K，则返回的范围长度为 0，根据容器的内部比较对象(key_comp)，两个迭代器都指向大于 K 的第一个元素。如果键超过了集合容器中的最大元素，它将返回一个迭代器，指向集合容器中的最后一个元素。

下面的程序说明了上面的功能。

```cpp
// CPP program to demonstrate the
// set::equal_range() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    set<int> s;

    s.insert(1);
    s.insert(4);
    s.insert(2);
    s.insert(5);
    s.insert(3);

    // prints the set elements
    cout << "The set elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // Function returns lower bound and upper bound
    auto it = s.equal_range(2);
    cout << "\nThe lower bound of 2 is " << *it.first;
    cout << "\nThe upper bound of 2 is " << *it.second;

    // Function returns the last element
    it = s.equal_range(8);
    cout << "\nThe lower bound of 8 is " << *it.first;
    cout << "\nThe upper bound of 8 is " << *it.second;

    // Function returns the range where the
    // element greater than 0 lies
    it = s.equal_range(0);
    cout << "\nThe lower bound of 0 is " << *it.first;
    cout << "\nThe upper bound of 0 is " << *it.second;

    return 0;
}
```

**Output:**

```cpp
The set elements are: 1 2 3 4 5 
The lower bound of 2 is 2
The upper bound of 2 is 3
The lower bound of 8 is 5
The upper bound of 8 is 5
The lower bound of 0 is 1
The upper bound of 0 is 1

```