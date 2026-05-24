# 以键作为用户定义数据类型的 C++ 映射

> 原文:[https://www . geesforgeks . org/c-map-key-user-define-data-type/](https://www.geeksforgeeks.org/c-map-key-user-define-data-type/)

[C++ 映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)以有序的形式存储密钥(注意，它在内部使用自平衡二叉查找树)。排序是使用运算符“<”在内部完成的。因此，如果我们使用自己的数据类型作为关键字，我们必须为我们的数据类型重载该运算符。

让我们考虑一个**映射**，其关键数据类型为结构，映射值为整数。

```cpp
// key's structure
struct key
{
    int a;
};
```

```cpp
// CPP program to demonstrate how a map can
// be used to have a user defined data type
// as key.
#include <bits/stdc++.h>
using namespace std;
struct Test {
    int id;
};

// We compare Test objects by their ids.
bool operator<(const Test& t1, const Test& t2)
{
    return (t1.id < t2.id);
}

// Driver code
int main()
{
    Test t1 = { 110 }, t2 = { 102 }, t3 = { 101 }, t4 = { 115 };

    // Inserting above four objects in an empty map
    map<Test, int> mp;
    mp[t1] = 1;
    mp[t2] = 2;
    mp[t3] = 3;
    mp[t4] = 4;

    // Printing Test objects in sorted order
    for (auto x : mp)
        cout << x.first.id << " " << x.second << endl;
    return 0;
}
```

**Output:**

```cpp
101 3
102 2
110 1
115 4

```

我们还可以使< operator 成为结构/类的成员。

```cpp
// With < operator defined as member method.
#include <bits/stdc++.h>
using namespace std;
struct Test {
    int id;

    // We compare Test objects by their ids.
    bool operator<(const Test& t) const
    {
        return (this->id < t.id);
    }
};

// Driver code
int main()
{
    Test t1 = { 110 }, t2 = { 102 }, t3 = { 101 }, t4 = { 115 };

    // Inserting above four objects in an empty map
    map<Test, int> mp;
    mp[t1] = 1;
    mp[t2] = 2;
    mp[t3] = 3;
    mp[t4] = 4;

    // Printing Test objects in sorted order
    for (auto x : mp)
        cout << x.first.id << " " << x.second << endl;
    return 0;
}
```

**Output:**

```cpp
101 3
102 2
110 1
115 4

```

**如果我们不超载<操作员会怎么样？**
如果我们试图在地图中插入任何东西，就会出现编译器错误。

```cpp
#include <bits/stdc++.h>
using namespace std;
struct Test {
    int id;
};

// Driver code
int main()
{
    map<Test, int> mp;
    Test t1 = {10};
    mp[t1] = 10;
    return 0;
}
```

**Output:**

```cpp
/usr/include/c++/5/bits/stl_function.h:387:20: error: no match for 'operator<' (operand types are 'const Test' and 'const Test')
       { return __x < __y; }

```