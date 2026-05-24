# c++ STL 中的无序 _ 集桶 _ 计数()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-bucket _ count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-bucket_count-function-in-c-stl/)

**无序集::桶计数()**方法是 C++ STL 中的内置函数，它返回无序集容器中存在的桶的总数。

*桶*是无序集的内部哈希表中存储元素的一个槽。

**注**:无序 _ 集合中的桶从 0 到 n-1 进行编号，其中 n 为桶的总数。

**语法**:

```cpp
*unordered_set_name*.bucket_count();

```

**参数**:本功能不接受任何参数。

**返回值**:该函数返回无序集容器中当前存在的桶数。

下面的程序说明了无序 _ 集合::bucket_count()函数:

```cpp
// CPP program to illustrate the
// unordered_set::bucket_count() function

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

    cout << "The sampleSet container has " << sampleSet.bucket_count()
         << " number of buckets\n\n";

    for (auto itr = sampleSet.begin(); itr != sampleSet.end(); itr++) {
        cout << "The Element " << (*itr) << " is present in the bucket: "
             << sampleSet.bucket(*itr);
        cout << endl;
    }

    return 0;
}
```

**输出:**

```cpp
The sampleSet container has 11 number of buckets

The Element 25 is present in the bucket: 3
The Element 5 is present in the bucket: 5
The Element 10 is present in the bucket: 10
The Element 15 is present in the bucket: 4
The Element 20 is present in the bucket: 9

```