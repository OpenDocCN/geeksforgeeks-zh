# c++ STL 中的多集侵位 _ 提示()函数

> 原文:[https://www . geesforgeks . org/multist-侵位 _hint-function-in-c-stl/](https://www.geeksforgeeks.org/multiset-emplace_hint-function-in-c-stl/)

**多集::侵位 _ 提示()**是 C++ STL 中的一个内置函数，它在多集中插入一个新元素。在函数的参数中传递一个位置，作为在当前位置插入元素之前从何处开始搜索操作的提示。位置只是帮助过程变得更快，它并不决定新元素插入的位置。新元素仅插入在多集容器的属性之后。

**语法:**

```cpp
multiset_name.emplace_hint(iterator position, value)
```

**参数:**该功能接受两个强制参数，如下所述:

*   **位置:**该参数作为在当前位置插入元素之前从何处进行搜索操作的提示。位置只是帮助过程更快，它并不决定新元素插入的位置。新元素仅插入在多集容器的属性之后。
*   **值:**指定要插入多集容器的元素。

**返回值:**函数返回一个迭代器，指向插入完成的位置。

下面的程序说明了上面的功能。

**程序 1:**

```cpp
// CPP program to demonstrate the
// multiset::emplace_hint() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;
    auto it = s.emplace_hint(s.begin(), 1);

    // stores the position of 2's insertion
    it = s.emplace_hint(it, 2);

    // fast step as it directly
    // starts the search step from
    // position where 2 was last inserted
    s.emplace_hint(it, 4);

    // this is a slower step as
    // it starts checking from the
    // position where 4 was inserted
    // but 3 is to be inserted before 4
    s.emplace_hint(it, 3);

    // prints the multiset elements
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
1 2 3 4

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// multiset::emplace_hint() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;
    auto it = s.emplace_hint(s.begin(), 1);

    // stores the position of 2's insertion
    it = s.emplace_hint(it, 2);

    // fast step as it directly
    // starts the search step from
    // position where 2 was last inserted
    s.emplace_hint(it, 4);

    // this is a slower step as
    // it starts checking from the
    // position where 4 was inserted
    // but 3 is to be inserted before 4
    s.emplace_hint(it, 3);

    // slower steps
    s.emplace_hint(s.begin(), 6);
    s.emplace_hint(s.begin(), 6);
    s.emplace_hint(s.begin(), 6);
    s.emplace_hint(s.begin(), 6);

    // prints the multiset elements
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
1 2 3 4 6 6 6 6

```