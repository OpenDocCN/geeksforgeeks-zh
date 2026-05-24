# c++ STL 中的无序 _ 集合 insert()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-insert-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-insert-function-in-c-stl/)

无序集::insert()是 C++ STL 中的内置函数，用于在无序集容器中插入新的{element}。只有当每个元素不等同于容器中已经存在的任何其他元素(无序集中的元素具有唯一的值)时，才会插入该元素。插入会根据容器的标准在该位置自动完成。这通过插入的元素数量有效地增加了容器的大小。
**语法:**

```cpp
unordered_set_name.insert (Value)

or,

unordered_set_name.insert (InputIterator first, InputIterator last)
```

**参数:**

*   **值**:指定要插入容器的值。
*   **第一个**、**最后一个**:指定元素范围的迭代器。范围[第一个，最后一个]中元素的副本被插入无序集容器中。请记住，范围包括第一个和最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。

**返回值:**函数返回一个对，其成员对::首先被设置为一个迭代器，指向新插入的元素或者已经在集合中的等价元素。如果插入了新元素，则该对中的第二个元素被设置为 true 如果已经存在等效元素，则设置为 false。
以下程序说明上述功能:
**程序 1** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
#include <string>
#include <unordered_set>
using namespace std;

int main()
{
    unordered_set<string> mySet = { "first", "third" };

    string myString = "tenth";

    // inserts key in set
    mySet.insert(myString);

    cout << "My set contains:"
         << endl;
    for (const string& x : mySet) {
        cout << x
             << " ";
    }

    cout << endl;
    return 0;
}
```

**Output**

```cpp
My set contains:
tenth first third 
```