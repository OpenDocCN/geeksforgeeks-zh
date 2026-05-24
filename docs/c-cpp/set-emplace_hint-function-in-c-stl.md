# 在 C++ STL 中设置侵位 _ 提示()函数

> 原文:[https://www . geesforgeks . org/set-侵位 _ 提示-function-in-c-stl/](https://www.geeksforgeeks.org/set-emplace_hint-function-in-c-stl/)

**集合::侵位 _ 提示()**是 C++ STL 中的一个内置函数，它在集合中插入一个新元素。在函数的参数中传递一个位置，作为在当前位置插入元素之前从何处开始搜索操作的提示。位置只是帮助过程变得更快，它并不决定新元素插入的位置。新元素仅插入集合容器的属性之后。

**语法:**

```cpp
set_name.emplace_hint(iterator position, value) 

```

**参数:**该函数接受两个强制参数，如下所述:

*   **Location:** This parameter is used as a prompt for searching before inserting elements in the current location. The location is just that the help process is faster, and it does not determine where the new element is inserted. The new element is inserted only after the property of the collection container.
*   **Value:** Specifies the element to be inserted into the collection container. If the value does not exist before, the value is inserted into the collection.

**返回值:**函数返回一个迭代器，指向插入完成的位置。如果参数中传递的元素已经存在，那么它会返回一个迭代器，指向现有元素所在的位置。

下面的程序说明了上面的功能。

```cpp
// CPP program to demonstrate the
// set::emplace_hint() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    set<int> s;
    auto it = s.emplace_hint(s.begin(), 1);

    // stores the position of 2's insertion
    it = s.emplace_hint(it, 2);

    // fast step as it directly
    // starts the search step from
    // position where 3 was last inserted
    s.emplace_hint(it, 3);

    // this is a slower step as
    // it starts checking from the
    // position where 3 was inserted
    // but 0 is to be inserted before 1
    s.emplace_hint(it, 0);

    // prints the set elements
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
0 1 2 3

```