# C++ STL 中的 multiset insert() 函数

> 原文: [https://www.geeksforgeeks.org/multiset-insert-function-in-c-stl/](https://www.geeksforgeeks.org/multiset-insert-function-in-c-stl/)

`multiset::insert()` 是 C++ STL 中的内置函数，它在 multiset 容器中插入元素，或者将元素从一个位置插入到另一个位置，从一个 multiset 插入到不同的 multiset。

## 语法

```cpp
iterator multiset_name.insert(element)
```

**参数:** 该函数接受一个强制参数 `element`，该元素将被插入到 multiset 容器中。

**返回值:** 函数返回一个迭代器，指向 multiset 容器中插入的元素。

下面的程序说明了上面的功能:

## C++

```cpp
// C++ program to demonstrate the
// multiset::insert(element) function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Function to insert elements
    // in the set container
    s.insert(1);
    s.insert(4);
    s.insert(1);
    s.insert(5);
    s.insert(1);

    cout << "The elements in multiset are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
The elements in multiset are: 1 1 1 4 5
```

## 语法

```cpp
iterator multiset_name.insert(iterator position, element)
```

**参数:** 该函数接受两个参数，如下所述:

*   **Element:** 它指定要插入到 multiset 容器中的元素。
*   **Location:** 它不指定插入的位置，只指向开始搜索操作的位置以使过程更快。插入是根据 multiset 容器遵循的顺序完成的。

**返回值:** 函数返回一个迭代器，指向 multiset 容器中插入的元素。

下面的程序说明了上面的功能:

## C++

```cpp
// C++ program to demonstrate the
// multiset::insert(iterator, element) function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s;

    // Function to insert elements
    // in the set container
    auto itr = s.insert(s.begin(), 1);

    // the time taken to insertion
    // is very less as the correct
    // position for insertion is given
    itr = s.insert(itr, 4);
    itr = s.insert(itr, 1);
    itr = s.insert(itr, 5);

    // Slow insertion as position is
    // not given correctly
    itr = s.insert(s.begin(), 3);

    cout << "The elements in multiset are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
The elements in multiset are: 1 1 3 4 5
```

## 语法

```cpp
iterator multiset_name.insert(iterator position1, iterator position2)
```

**参数:** 该函数接受两个参数 `position1` 和 `position2`，指定元素的范围。范围 `[position1, last]` 中的所有元素都被插入到另一个 multiset 容器中。

**返回值:** 该函数返回一个 multiset，该 multiset 包含范围内的所有元素 `[position1, last]`。

下面的程序说明了上面的功能:

## C++

```cpp
// C++ program to demonstrate the
// multiset::insert(iterator position1, iterator position2) function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    multiset<int> s1;

    // Function to insert elements
    // in the set container
    s1.insert(1);
    s1.insert(4);
    s1.insert(1);
    s1.insert(5);
    s1.insert(1);
    s1.insert(3);

    cout << "The elements in multiset1 are: ";
    for (auto it = s1.begin(); it != s1.end(); it++)
        cout << *it << " ";

    multiset<int> s2;

    // Function to insert one multiset to another
    // all elements from where 3 is to end is
    // inserted to multiset2
    s2.insert(s1.find(3), s1.end());

    cout << "\nThe elements in multiset2 are: ";
    for (auto it = s2.begin(); it != s2.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
The elements in multiset1 are: 1 1 1 3 4 5
The elements in multiset2 are: 3 4 5
```