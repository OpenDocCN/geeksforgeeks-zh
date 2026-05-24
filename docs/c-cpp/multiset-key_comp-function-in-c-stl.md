# c++ STL 中的多集 key_comp()函数

> 原文:[https://www . geesforgeks . org/multist-key _ comp-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-key_comp-function-in-c-stl/)

**STD::multist::key _ comp()**是 **C++ STL** 中的一个内置函数，它返回容器使用的比较对象的副本。默认情况下，这是一个 less 对象，返回与运算符“<”相同的值。它是一个函数指针或函数对象，接受两个与容器元素类型相同的参数，如果第一个参数被认为在它定义的严格弱排序中位于第二个参数之前，则返回 true，否则返回 false。如果 key_comp 反身返回 false(即，无论键作为参数传递的顺序如何)，则两个键被认为是等效的。

**语法:**

```cpp
key_compare multiset_name.key_comp();

```

**参数:**本功能不接受任何参数。

**返回值:**该函数返回容器使用的比较对象的一个**副本。**

以下示例说明了 multist::key _ comp()方法:

**例 1 :**

```cpp
// C++ program to illustrate the
// multiset::key_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a multiset named m;
    multiset<int> m;

    multiset<int>::key_compare
        comp
        = m.key_comp();

    // Inserting elements into multiset
    m.insert(10);
    m.insert(20);
    m.insert(30);
    m.insert(40);

    cout << "Multiset has the elements\n";

    // Store key value of last element
    int highest = *m.rbegin();

    // initializing the iterator
    multiset<int>::iterator it = m.begin();

    // printing elements of all multiset
    do {

        cout << " " << *it;

    } while (comp(*it++, highest));

    return 0;
}
```

**Output:**

```cpp
Multiset has the elements
 10 20 30 40

```

**例 2 :**

```cpp
// C++ program to illustrate the
// multiset::key_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a multiset named m;
    multiset<int> m;

    multiset<int>::key_compare
        comp
        = m.key_comp();

    // Inserting elements into multiset
    m.insert(100);
    m.insert(200);
    m.insert(300);
    m.insert(400);

    cout << "Multiset has the elements\n";

    // Store key value of last element
    int highest = *m.rbegin();

    // initializing the iterator
    multiset<int>::iterator it = m.begin();

    // printing elements of all multiset
    do {

        cout << " " << *it;

    } while (comp(*it++, highest));

    return 0;
}
```

**Output:**

```cpp
Multiset has the elements
 100 200 300 400

```