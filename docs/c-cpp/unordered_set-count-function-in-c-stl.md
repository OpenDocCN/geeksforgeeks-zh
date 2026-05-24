# c++ STL 中的无序 _ 集合计数()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-count-function-in-c-stl/)

**无序集::count()** 函数是 C++ STL 中的内置函数，用于统计无序集容器中特定元素的出现次数。由于无序集容器不允许存储重复的元素，因此该函数通常用于检查容器中是否存在元素。如果元素存在于容器中，函数返回 1，否则返回 0。
**语法** :

```cpp
*unordered_set_name*.count(element)
```

**参数**:本功能接受单个参数*元素*。此参数表示容器中是否存在需要检查的元素。
**返回值**:如果容器中存在元素，则该函数返回 1，否则返回 0。
**时间复杂度**:对于*无序 _ 集合::count()* 方法的时间复杂度在平均情况下为 O(1)，但在最坏的情况下，时间复杂度可以为 O(N)，即 Linear，其中 N 为容器的大小。

以下程序说明了*无序 _ 集合::计数()*功能:

**程序 1** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate the
// unordered_set::count() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<int> sampleSet;

    // Inserting elements
    sampleSet.insert(5);
    sampleSet.insert(10);
    sampleSet.insert(15);
    sampleSet.insert(20);
    sampleSet.insert(25);

    // displaying all elements of sampleSet
    cout << "sampleSet contains: ";
    for (auto itr = sampleSet.begin(); itr != sampleSet.end(); itr++) {
        cout << *itr << " ";
    }

    // checking if element 20 is present in the set
    if (sampleSet.count(20) == 1) {
        cout << "\nElement 20 is present in the set";
    }
    else {
        cout << "\nElement 20 is not present in the set";
    }

    return 0;
}
```

**Output:** 

```cpp
sampleSet contains: 25 5 10 15 20 
Element 20 is present in the set
```

**节目 2** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// unordered_set::count() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<string> sampleSet;

    // Inserting elements
    sampleSet.insert("Welcome");
    sampleSet.insert("To");
    sampleSet.insert("GeeksforGeeks");
    sampleSet.insert("Computer Science Portal");
    sampleSet.insert("For Geeks");

    // displaying all elements of sampleSet
    cout << "sampleSet contains: ";
    for (auto itr = sampleSet.begin(); itr != sampleSet.end(); itr++) {
        cout << *itr << " ";
    }

    // checking if element GeeksforGeeks is
    // present in the set
    if (sampleSet.count("GeeksforGeeks") == 1) {
        cout << "\nGeeksforGeeks is present in the set";
    }
    else {
        cout << "\nGeeksforGeeks is not present in the set";
    }

    return 0;
}
```

**Output:** 

```cpp
sampleSet contains: Welcome To GeeksforGeeks For Geeks Computer Science Portal 
GeeksforGeeks is present in the set
```