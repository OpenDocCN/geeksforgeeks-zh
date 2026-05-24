# C++ STL 中的 `unordered_set::bucket_count()` 函数

> 原文：[https://www.geeksforgeeks.org/unordered_set-bucket_count-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-bucket_count-function-in-c-stl/)

`unordered_set::bucket_count()` 方法是 C++ STL 中的内置函数，它返回 `unordered_set` 容器中存在的桶的总数。

*桶*是 `unordered_set` 的内部哈希表中存储元素的一个槽。

**注**：`unordered_set` 中的桶从 0 到 n-1 进行编号，其中 n 为桶的总数。

## 语法

```cpp
*unordered_set_name*.bucket_count();
```

## 参数

本功能不接受任何参数。

## 返回值

该函数返回 `unordered_set` 容器中当前存在的桶数。

## 示例程序

下面的程序说明了 `unordered_set::bucket_count()` 函数：

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

## 输出

```cpp
The sampleSet container has 11 number of buckets

The Element 25 is present in the bucket: 3
The Element 5 is present in the bucket: 5
The Element 10 is present in the bucket: 10
The Element 15 is present in the bucket: 4
The Element 20 is present in the bucket: 9
```