# 如何反向遍历一张 STL 图？

> 原文:[https://www . geesforgeks . org/如何反向遍历 a-STL-map/](https://www.geeksforgeeks.org/how-to-traverse-a-stl-map-in-reverse-direction/)

[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)按照键的排序顺序存储元素。现在，如果我们想以相反的顺序遍历它，我们将使用 map 的 reverse_iterator。

语法:

```cpp
map::reverse_iterator iterator_name;

```

地图的反向迭代器按增量向后移动。因此，我们将 reverse_iterator 指向 map 的最后一个元素，然后继续递增，直到它到达第一个元素。为此，我们将使用 std::map 的 2 个成员函数，即
1。rbegin():它返回指向地图最后一个元素的 reverse_iterator。
2。rend():它返回指向地图第一个元素的 reverse_iterator。

现在，为了以相反的顺序遍历，我们将使用 reverse_iterator 迭代 b/w rbegin() & rend()范围。
**地图中的反向迭代:**
示例:

```cpp
Input:  (10, "geeks"), (20, "practice"),  (5, " contribute")
Output : (20, "practice"),  (10, "geeks"), (5, " contribute")

```

```cpp
// C++ program makes a map to iterate
// elements in reverse order.
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating & Initializing a map of String & Ints
    map<int, string> mymap;

    // Inserting the elements one by one
    mymap.insert(make_pair(10, "geeks"));
    mymap.insert(make_pair(20, "practice"));
    mymap.insert(make_pair(5, "contribute"));

    // Create a map reverse iterator
    map<int, string>::reverse_iterator it;

    // rbegin() returns to the last value of map
    for (it = mymap.rbegin(); it != mymap.rend(); it++) {
        cout << "(" << it->first << ", " 
             << it->second << ")" << endl;
    }

    return 0;
}
```

**Output:**

```cpp
(20, practice)
(10, geeks)
(5, contribute)

```

我们也可以使用 auto 来避免记住复杂的语法。

```cpp
// C++ program makes a map to iterate
// elements in reverse order with simpler
// syntax
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating & Initializing a map of String & Ints
    map<int, string> mymap;

    // Inserting the elements one by one
    mymap.insert(make_pair(10, "geeks"));
    mymap.insert(make_pair(20, "practice"));
    mymap.insert(make_pair(5, "contribute"));

    // rbegin() returns to the last value of map
    for (auto it = mymap.rbegin(); it != mymap.rend(); it++) {
        cout << "(" << it->first << ", " 
             << it->second << ")" << endl;
    }

    return 0;
}
```

**Output:**

```cpp
(20, practice)
(10, geeks)
(5, contribute)

```

**反向迭代在[多贴图](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/) :**
多贴图类似于贴图，增加了多个元素可以有相同的关键点。在这种情况下，键值和映射值对必须是唯一的，而不是每个元素都是唯一的。

示例:

```cpp
Input :  (10, "geeks"), (20, "practice"),  (5, "contribute"), 
         (20, "van"), (20, "watch"), (5, "joker")
Output:  (20, "watch"), (20, "van"), (20, "practice"), 
         (10, "geeks"), (5, "joker"), (5, "contribute")

```

```cpp
// C++ program makes a multimap to store
// elements in descending order.
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating & Initializing a multimap 
    // of Ints & String
    multimap<int, std::string> mymap;

    // Inserting the elements one by one
    mymap.insert(make_pair(10, "geeks"));
    mymap.insert(make_pair(20, "practice"));
    mymap.insert(make_pair(5, "contribute"));

    // Duplicates allowed
    mymap.insert(make_pair(20, "van")); 

    mymap.insert(make_pair(20, "watch"));
    mymap.insert(make_pair(5, "joker"));

    for (auto it = mymap.rbegin(); it != mymap.rend(); it++) {
        cout << "(" << it->first << ", " 
            << it->second << ")" << endl;
    }

    return 0;
}
```

**Output:**

```cpp
(20, watch)
(20, van)
(20, practice)
(10, geeks)
(5, joker)
(5, contribute)

```