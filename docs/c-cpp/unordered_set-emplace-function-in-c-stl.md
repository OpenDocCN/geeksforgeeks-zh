# c++ STL 中的无序 _set 侵位()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-侵位-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-emplace-function-in-c-stl/)

**无序 _ 集合::侵位()**函数是 C++ STL 中的内置函数，用于在无序 _ 集合容器中插入元素。仅当元素尚未出现在容器中时，才会插入该元素。这种插入也有效地增加了容器尺寸 1。

**语法**:

```cpp
*unordered_set_name*.emplace(element)
```

**参数**:该函数接受单个参数*元素*，该元素将被插入无序集容器中。

**返回值**:该函数在成功插入时返回一对。这对由一个指向新插入元素的迭代器和一个布尔值*真*组成。如果要插入的元素已经存在于容器中，那么它返回一个包含指向已经存在的元素的迭代器和布尔值 *false* 的对。

以下程序说明了*无序 _ 设置::定位()*功能:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_set::emplace() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<int> sampleSet;

    // Inserting elements
    sampleSet.emplace(5);
    sampleSet.emplace(10);
    sampleSet.emplace(15);
    sampleSet.emplace(20);
    sampleSet.emplace(25);

    // displaying all elements of sampleSet
    cout << "sampleSet contains: ";
    for (auto itr = sampleSet.begin(); itr != sampleSet.end(); itr++) {
        cout << *itr << " ";
    }

    return 0;
}
```

**Output:**

```cpp
sampleSet contains: 25 5 10 15 20

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_set::emplate() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<string> sampleSet;

    // Inserting elements using
    // emplace() function
    sampleSet.emplace("Welcome");
    sampleSet.emplace("To");
    sampleSet.emplace("GeeksforGeeks");
    sampleSet.emplace("Computer Science Portal");
    sampleSet.emplace("For Geeks");

    // displaying all elements of sampleSet
    cout << "sampleSet contains: ";
    for (auto itr = sampleSet.begin(); itr != sampleSet.end(); itr++) {
        cout << *itr << " ";
    }

    return 0;
}
```

**Output:**

```cpp
sampleSet contains: Welcome To GeeksforGeeks For Geeks Computer Science Portal

```