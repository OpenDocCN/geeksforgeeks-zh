# c++ STL 中的多映射键 _comp()

> 原文:[https://www.geeksforgeeks.org/multimap-key_comp-in-c-stl/](https://www.geeksforgeeks.org/multimap-key_comp-in-c-stl/)

**STD::multimap::key _ comp()**是 C++ STL 中的一个内置函数，它返回容器使用的比较对象的副本。默认情况下，这是一个 less 对象，返回与运算符“<”相同的值。它是一个函数指针或函数对象，接受两个与容器元素类型相同的参数，如果第一个参数被认为在它定义的严格弱排序中位于第二个参数之前，则返回 true，否则返回 false。如果 key_comp 反身返回 false(即，无论键作为参数传递的顺序如何)，则两个键被认为是等效的。

**语法:**

```cpp
key_compare multimap_name.key_comp();
```

**参数:**此功能不接受任何参数。

**返回值:**函数返回容器使用的比较对象的副本。

以下示例说明了 multimap::key_comp()方法:

**例 1:**

```cpp
// C++ program to illustrate the
// multimap::key_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a multimap named m;
    multimap<char, int> m;

    multimap<char, int>::key_compare
        comp
        = m.key_comp();

    // Inserting elements into multimap
    m.insert(make_pair('a', 10));
    m.insert(make_pair('b', 20));
    m.insert(make_pair('c', 30));
    m.insert(make_pair('d', 40));

    cout << "Multimap has the elements\n";

    // Store key value of last element
    char l = m.rbegin()->first;

    // initializing the iterator
    map<char, int>::iterator it = m.begin();

    // printing elements of all multimap
    do {

        cout << it->first
             << " => "
             << it->second
             << '\n';

    } while (comp((*it++).first, l));

    return 0;
}
```

**Output:**

```cpp
Multimap has the elements
a => 10
b => 20
c => 30
d => 40

```

**例 2:**

```cpp
// C++ program to illustrate the
// multimap::key_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a multimap named m;
    multimap<char, int> m;

    multimap<char, int>::key_compare
        comp
        = m.key_comp();

    // Inserting elements into multimap
    m.insert(make_pair('a', 100));
    m.insert(make_pair('b', 200));
    m.insert(make_pair('c', 300));
    m.insert(make_pair('d', 400));

    cout << "Multimap has the elements\n";

    // Store key value of last element
    char l = m.rbegin()->first;

    // initializing the iterator
    map<char, int>::iterator it = m.begin();

    // printing elements of all multimap
    do {

        cout << it->first
             << " => "
             << it->second
             << '\n';

    } while (comp((*it++).first, l));

    return 0;
}
```

**Output:**

```cpp
Multimap has the elements
a => 100
b => 200
c => 300
d => 400

```