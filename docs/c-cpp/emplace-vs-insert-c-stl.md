# 在 C++ STL 中定位与插入

> 哎哎哎:# t0]https://www . geeksforgeeks . org/emplace-vs-insert-c-STL/

在 C++ 中，所有容器([向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)、[堆栈](https://www.geeksforgeeks.org/stack-in-cpp-stl/)、[队列](https://www.geeksforgeeks.org/queue-cpp-stl/)、[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)、[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)等)都支持插入和就位操作。
侵位的好处是，它做到了原地插入，避免了不必要的复制物体。对于原始数据类型，我们使用哪一种并不重要。但是对于物体来说，出于效率的原因，最好使用炮台()。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate difference between
// emplace and insert
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // declaring map
    multiset<pair<char, int>> ms;

    // using emplace() to insert pair in-place
    ms.emplace('a', 24);

    // Below line would not compile
    // ms.insert('b', 25);   

    // using insert() to insert pair in-place
    ms.insert(make_pair('b', 25));   

    // printing the multiset
    for (auto it = ms.begin(); it != ms.end(); ++ it)
        cout << " " << (*it).first << " "
             << (*it).second << endl;

    return 0;
}
```

输出:

```cpp
 a 24
 b 25
```

详见[在 std::map 中插入元素(插入、就位和操作员[])](https://www.geeksforgeeks.org/inserting-elements-in-stdmap-insert-emplace-and-operator/) 。