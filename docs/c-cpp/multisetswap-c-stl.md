# c++ STL 中的多集::swap()

> 原文:[https://www.geeksforgeeks.org/multisetswap-c-stl/](https://www.geeksforgeeks.org/multisetswap-c-stl/)

[多集合](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)是一种类似于集合的关联容器，不同的是多个元素可以有相同的值。

**多集::swap()**

此函数用于交换两个多集的内容，但是集必须是相同类型的，尽管大小可能不同。

**语法:**

```cpp
*multisetname1*.swap(*multisetname2*)
Parameters :
The name of the multiset with which
the contents have to be swapped.

Result :
All the elements of the 2 multiset are swapped.

```

示例:

```cpp
Input  : multiset1 = {1, 2, 3, 4}
         multiset2 = {5, 6, 7, 8}
         multiset1.swap(multiset2);
Output : multiset1 = {5, 6, 7, 8}
         multiset2 = {1, 2, 3, 4}

Input  : multiset1 = {'a', 'b', 'c', 'd'}
         multiset2 = {'w', 'x', 'y', 'z'}
         multiset1.swap(multiset2);
Output : multiset1 = {'w', 'x', 'y', 'z'}
         multiset2 = {'a', 'b', 'c', 'd'}

```

```cpp
// INTEGER MULTISET EXAMPLE
// CPP program to illustrate
// Implementation of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two multisets
    multiset<int> multiset1{ 1, 2, 3, 4 };
    multiset<int> multiset2{ 5, 6, 7, 8 };

    // Swap elements of multisets
    multiset1.swap(multiset2);

    // Print the first multi set
    cout << "multiset1 = ";
    for (auto it = multiset1.begin();
         it != multiset1.end(); ++ it)
        cout << ' ' << *it;

    // Print the second multiset
    cout << endl
         << "multiset2 = ";
    for (auto it = multiset2.begin();
         it != multiset2.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
multiset1 =  5 6 7 8
multiset2 =  1 2 3 4
```

```cpp
// STRING MULTISET EXAMPLE
// CPP program to illustrate
// Implementation of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two multisets
    multiset<string> multiset1{ "Geeksforgeeks" };

    multiset<string> multiset2{ "Computer scince", "Portal" };

    // Swap elements of multisets
    multiset1.swap(multiset2);

    // Print the first multi set
    cout << "multiset1 = ";
    for (auto it = multiset1.begin();
         it != multiset1.end(); ++ it)
        cout << ' ' << *it;

    // Print the second multiset
    cout << endl
         << "multiset2 = ";
    for (auto it = multiset2.begin();
         it != multiset2.end(); ++ it)
        cout << '
```

输出:

```cpp
multiset1 =  Computer science portal
multiset2 =  Geeksforgeeks
```

```cpp
// CHARACTER MULTISET EXAMPLE
// CPP program to illustrate
// Implementation of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two multisets
    multiset<char> multiset1{ 'A', 'B', 'C' };
    multiset<char> multiset2{ 'G', 'H', 'I' };

    // Swap elements of multisets
    multiset1.swap(multiset2);

    // Print the first multi set
    cout << "multiset1 = ";
    for (auto it = multiset1.begin();
         it != multiset1.end(); ++ it)
        cout << ' ' << *it;

    // Print the second multiset
    cout << endl
         << "multiset2 = ";
    for (auto it = multiset2.begin();
         it != multiset2.end(); ++ it)
        cout << ' ' << *it;

    re
```

输出:

```cpp
multiset1 =  G H I
multiset2 =  A B C
```

**时间复杂度:**常数