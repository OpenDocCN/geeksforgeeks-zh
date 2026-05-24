# c++ STL 中无序 _ 集合相等 _ 范围

> 原文:[https://www . geesforgeks . org/unordered _ set-equal _ range-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-equal_range-in-c-stl/)

[equal_range()](https://www.geeksforgeeks.org/equal_range-in-cpp/) 一般返回包含所有等于给定值的元素的范围。对于所有键都不同的[无序集](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)，返回的范围最多包含一个元素。

**语法**

```cpp
 setname.equal_range(key name)

```

**参数**
它以要搜索的关键字为参数。
**返回值**
它返回两个迭代——包含该键的范围的下限和上限。
**示例**

```cpp
// C++ program to illustrate the
// unordered_set::equal_range function
#include <iostream>
#include <unordered_set>
using namespace std;
int main()
{
    // declaration
    unordered_set<int> sample;

    // Insert some values
    sample.insert({ 20, 30, 40 });

    // Test the equal_range function for
    // a given key if it does exists
    auto range1 = sample.equal_range(20);
    if (range1.first != sample.end()) {
        for (; range1.first != range1.second; ++ range1.first)
            cout << *range1.first << endl;
    }
    else
        cout << "Element does not exist";
    return 0;
}
```

**输出**

```cpp
20
```

```cpp
// C++ program to illustrate the
// unordered_set::equal_range function
#include <iostream>
#include <unordered_set>
using namespace std;
int main()
{

    // declaration
    unordered_set<int> sample;

    // Insert some values
    sample.insert({ 20, 30, 40 });

    // Test the equal_range function 
    // for a given key if it does not exist
    auto range1 = sample.equal_range(60);
    if (range1.first != sample.end()) {
        for (; range1.first != range1.second; ++ range1.first)
            cout << *range1.first << endl;
    }
    else
        cout << "Element does not exist";
    return 0;
}
```

**输出**

```cpp
Element does not exist

```