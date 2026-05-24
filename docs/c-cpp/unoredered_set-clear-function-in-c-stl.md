# c++ STL 中的无序 _set clear()函数

> 原文:[https://www . geesforgeks . org/uno federed _ set-clear-function-in-c-STL/](https://www.geeksforgeeks.org/unoredered_set-clear-function-in-c-stl/)

**无序 _ 集合::clear()** 函数是 C++ STL 中的一个内置函数，用来清除一个无序 _ 集合容器。也就是说，这个函数从无序集中移除所有元素并清空它。所有迭代器、指针和对容器的引用都将失效。这将容器的大小减小到零。

**语法**:

```cpp
*unordered_set_name*.clear()
```

**参数**:本功能不接受任何参数。
**返回值**:该函数不返回值。
以下程序说明了*无序 _ 设置::清除()*功能:
**程序 1** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// unordered_set::clear() function

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

    // clear the set
    sampleSet.clear();

    // size after clearing
    cout << "\nSize of set after clearing elements: "
         << sampleSet.size();

    return 0;
}
```

**Output**

```cpp
sampleSet contains: 25 20 15 5 10 
Size of set after clearing elements: 0
```

**程序 2** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// unordered_set::clear() function

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

    // clear the set
    sampleSet.clear();

    // size after clearing
    cout << "\nSize of set after clearing elements: "
         << sampleSet.size();

    return 0;
}
```

**Output**

```cpp
sampleSet contains: For Geeks GeeksforGeeks Computer Science Portal Welcome To 
Size of set after clearing elements: 0
```