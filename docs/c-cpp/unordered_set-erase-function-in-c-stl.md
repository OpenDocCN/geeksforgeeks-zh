# c++ STL 中的无序 _set erase()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-erase-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-erase-function-in-c-stl/)

[**无序 _set::erase()**](https://www.cplusplus.com/reference/unordered_set/unordered_set/erase/) 函数是 C++ STL 中的内置函数，用于移除从开始(包含)到结束(排除)的单个元素或一组元素。这将通过移除的元素数量来减小容器的大小。
**注**:无序 _ 集合中的桶从 0 到 n-1 编号，其中 n 为桶的总数。
**语法** :
可以用三种方式声明，

```cpp
Method(1): unordered_set_name.erase(iterator start, iterator end)

Method(2): unordered_set_name.erase(iterator position)

Method(3): unordered_set_name.erase(element)
```

**复杂度:**

<u>平均情况</u> : *线性*在去除的元素数量上(对于方法(2)和方法(3)是*常数*)。

<u>最差情况</u> : *线性*在集装箱大小。

**参数:**该函数接受三种类型的参数。如果它接受一个元素，那么它会找到那个特定的元素并删除它。如果它接受一个迭代器，那么它会删除该位置的元素。如果它接受两个迭代器开始和结束，它会删除范围[开始，结束]中的所有元素

**返回值**:这个函数返回一个迭代器，指向最后一个元素之后的元素，在前两个语法的情况下，这个元素被删除。在第三种语法的情况下，如果元素不在无序集中，则返回 0，否则在擦除元素后返回 1。

以下程序说明了**无序 _ 设置::擦除()**功能:
T3】程序 1 :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate the
// unordered_set::erase() function

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

    // erases a particular element by its position
    sampleSet.erase(sampleSet.find(10));

    // displaying the set after removal
    for (auto it = sampleSet.begin(); it != sampleSet.end(); it++) {
        cout << *it << " ";
    }

    // erases a range of elements
    sampleSet.erase(sampleSet.begin(), sampleSet.end());

    cout << "\nSet size: " << sampleSet.size();

    return 0;
}
```

**输出**:

```cpp
25 5 15 20  
Set size: 0
```

**程序 2** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate the
// unordered_set::erase() function

#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<string> sampleSet = { "geeks1", "for", "geeks2" };

    // erases a particular element
    sampleSet.erase("geeks1");

    // displaying the set after removal
    cout << "Elements: ";
    for (auto it = sampleSet.begin(); it != sampleSet.end(); it++) {
        cout << *it << " ";
    }

    sampleSet.insert("geeks1");
    // erases from where for is
    sampleSet.erase(sampleSet.find("for"), sampleSet.end());

    // displaying the set after removal
    cout << "\nAfter second removal set : ";
    for (auto it = sampleSet.begin(); it != sampleSet.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**输出**:

```cpp
Elements: geeks2 for 
After second removal set : geeks1 geeks2 
```