# c++ STL 中集合的映射，带示例

> 原文:[https://www . geeksforgeeks . org/c-STL-带示例的集合图/](https://www.geeksforgeeks.org/map-of-sets-in-c-stl-with-examples/)

[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)是以映射方式存储元素的关联容器。每个元素都有一个**键**值和一个**映射**值。没有两个映射值可以有相同的**和**键值。

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是**唯一的**，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

STL 中的**集合图**:集合图在设计**复杂的**数据结构和算法时非常有用。

**语法:**

> map <datatype set="">> map_of_set:存储与一个数字对应的一组数字</datatype>
> 
> 或者
> 
> 映射<set>，数据类型>映射 _of_set:存储对应于一组数字的数字</set>

让我们看看如何在 C++ 中实现集合映射:

## C++

```cpp
// C++ program to demonstrate use of map of set

#include <bits/stdc++.h>
using namespace std;

void show(map<int, set<string> >& mapOfSet)
{
    // Using iterator to access
    // key, value pairs present
    // inside the mapOfSet
    for (auto it = mapOfSet.begin();
         it != mapOfSet.end();
         it++) {

        // Key is integer
        cout << it->first << " => ";

        // Value is a set of string
        set<string> st = it->second;

        // Strings will be printed
        // in sorted order as set
        // maintains the order
        for (auto it = st.begin();
             it != st.end(); it++) {
            cout << (*it) << ' ';
        }
        cout << '\n';
    }
}

// Driver code
int main()
{
    // Declaring a map whose key
    // is of integer type and
    // value is a set of string
    map<int, set<string> > mapOfSet;

    // Inserting values in the
    // set mapped with key 1
    mapOfSet[1].insert("Geeks");
    mapOfSet[1].insert("For");

    // Set stores unique or
    // distinct elements only
    mapOfSet[1].insert("Geeks");

    // Inserting values in the
    // set mapped with key 2
    mapOfSet[2].insert("Is");
    mapOfSet[2].insert("The");

    // Inserting values in the
    // set mapped with key 3
    mapOfSet[3].insert("Great");
    mapOfSet[3].insert("Learning");

    // Inserting values in the
    // set mapped with key 4
    mapOfSet[4].insert("Platform");

    show(mapOfSet);

    return 0;
}
```

**Output**

```cpp
1 => For Geeks 
2 => Is The 
3 => Great Learning 
4 => Platform 

```