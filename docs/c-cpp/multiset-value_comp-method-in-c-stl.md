# c++ STL 中的多集 value_comp()方法

> 原文:[https://www . geesforgeks . org/multist-value _ comp-method-in-c-STL/](https://www.geeksforgeeks.org/multiset-value_comp-method-in-c-stl/)

**STD::multist::value _ comp**是 C++ STL 中的一个内置函数，它返回容器使用的比较对象的副本。默认情况下，这是一个 less 对象，返回与运算符“<”相同的值。它是一个函数指针或函数对象，接受两个与容器元素类型相同的参数，如果第一个参数被认为在它定义的严格弱排序中位于第二个参数之前，则返回 true，否则返回 false。如果 key_comp 反身返回 false(即，无论键作为参数传递的顺序如何)，则两个键被认为是等效的。

**语法:**

```cpp
value_compare multiset_name.value_comp() 

```

**参数:**此功能不接受任何参数。

**返回值:**函数返回容器使用的比较对象的副本。

以下示例说明了上述方法:

**例 1:**

```cpp
// C++ program to illustrate the
// multiset::value_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a multiset named m;
    multiset<int> m;

    multiset<int>::value_compare
        comp
        = m.value_comp();

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

**例 2:**

```cpp
// C++ program to illustrate the
// multiset::value_comp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a multiset named m;
    multiset<int> m;

    multiset<int>::value_compare
        comp
        = m.value_comp();

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