# c++ STL 中的无序 _ 集桶 _ 大小()

> 原文:[https://www . geesforgeks . org/unordered _ set-bucket _ size-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-bucket_size-in-c-stl/)

无序集::bucket_size()函数是 C++ STL 中的内置函数，它返回无序集容器中特定存储桶中存在的元素总数。
*桶*是无序集的内部哈希表中存储元素的一个槽。
**注**:无序 _ 集合中的桶从 0 到 n-1 编号，其中 n 为桶的总数。
**语法**:

```cpp
*unordered_set*.bucket_size(n);

```

**参数**:该功能接受单个参数 **n** ，该参数为必选项。此参数表示需要查找元素总数的桶号。
**返回值**:该函数返回桶中存在的元素总数 *n* 。
下面的程序说明了无序 _ 集合::bucket_size()函数:
**程序 1** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate the
// unordered_set::bucket_size() function
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{

    unordered_set<int> sampleSet;

    // to store number of buckets
    int bucketCount;

    // Inserting elements
    sampleSet.insert(5);
    sampleSet.insert(10);
    sampleSet.insert(15);
    sampleSet.insert(20);
    sampleSet.insert(25);

    bucketCount = sampleSet.bucket_count();
    // displaying number of buckets
    cout << "sampleSet has " << bucketCount << " buckets\n";

    // displaying number of elements in bucket numbered 1
    cout << "Bucket number 3 contains "
         << sampleSet.bucket_size(3) << " elements";

    return 0;
}
```

**输出**:

```cpp
sampleSet has 7 buckets
Bucket number 3 contains 1 elements

```

**程序 2** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate the
// unordered_set::bucket_size() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<string> sampleSet;

    // to store number of buckets
    int bucketCount;

    // Inserting elements
    sampleSet.insert("Welcome");
    sampleSet.insert("To");
    sampleSet.insert("GeeksforGeeks");
    sampleSet.insert("Computer Science Portal");
    sampleSet.insert("For Geeks");

    bucketCount = sampleSet.bucket_count();
    // displaying number of buckets
    cout << "sampleSet has " << bucketCount << " buckets\n";

    // displaying number of elements in bucket numbered 0
    cout << "Bucket number 0 contains "
         << sampleSet.bucket_size(0) << " elements";

    return 0;
}
```

**输出**:

```cpp
sampleSet has 7 buckets
Bucket number 0 contains 0 elements 
```