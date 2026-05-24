# c++ STL 中的无序集 get 分配器()，示例

> 原文:[https://www . geesforgeks . org/unordered _ set-get _ 分配器-in-cpp-stl/](https://www.geeksforgeeks.org/unordered_set-get_allocator-in-cpp-stl/)

[无序集](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)的 get _ 分配器()方法是 C++ 的**标准模板库(STL)** 的一部分。此方法获取存储的分配器对象并返回它。

**语法:**

```cpp
Allocator_type get_allocator() const;
```

其中**分配器 _type** 是容器使用的分配器的类型。

**返回值:**返回用于构造容器的**分配器对象**。

**异常:**在这个方法中，如果有任何元素比较对象抛出异常，就会抛出异常。

下面的程序说明了*无序 _ 集合::get _ 分配器()*函数

**程序 1:**

```cpp
// CPP program to illustrate
// unordered_set get_allocator()

#include <iostream>
#include <unordered_set>

using namespace std;
int main()
{

    //'c' is object of 'unordered_set'
    unordered_set<int> c;

    //'allocator_type' is inherit in 'unordered_set'
    //'a' is object of 'allocator_type'
    //'get_allocator()' is member of 'unordered_set'
    unordered_set<int>::allocator_type a = c.get_allocator();

    // Comparing the Allocator with Pair<int, int>
    cout << "Is allocator Pair<int, int> : "
         << boolalpha
         << (a == allocator<pair<int, int> >());

    return 0;
}
```

**Output:**

```cpp
Is allocator Pair : true 
```

**复杂度:**
执行一个操作需要**常数(O(1))** 的时间复杂度。

**程序 2 :**

```cpp
// CPP program to illustrate
// unordered_set get_allocator()

#include <iostream>
#include <unordered_map>

using namespace std;

int main(void)
{
    unordered_map<char, int> um;
    pair<const char, int>* a;

    a = um.get_allocator().allocate(8);

    cout << "Allocated size = " << sizeof(*a) * 8 << endl;

    return 0;
}
```

**Output:**

```cpp
Allocated size = 64

```