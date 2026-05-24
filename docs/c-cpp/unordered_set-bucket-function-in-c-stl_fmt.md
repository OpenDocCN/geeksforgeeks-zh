# C++ STL 中的 unordered_set::bucket() 函数

> 原文: [https://www.geeksforgeeks.org/unordered_set-bucket-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-bucket-function-in-c-stl/)

`unordered_set::bucket()` 方法是 C++ STL 中的一个内置函数，返回特定元素的 bucket 编号。也就是说，该函数返回特定元素存储在无序集容器中的存储桶号。

*桶*是无序集的内部哈希表中存储元素的一个槽。

**注**: `unordered_set` 中的桶从 0 到 n-1 进行编号，其中 n 为桶的总数。

## 语法

```cpp
unordered_set_name.bucket(element);
```

## 参数

这是一个强制参数，指定 `unordered_set` 容器中需要知道其桶号的元素的值。

## 返回值

该函数返回存储有 `element` 元素的无序集容器中的桶的桶号。

## 程序示例

下面的程序说明了 `unordered_set::bucket()` 功能:

```cpp
// C++ program to illustrate the
// unordered_set::bucket() function

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
The Element 25 is present in the bucket: 3
The Element 5 is present in the bucket: 5
The Element 10 is present in the bucket: 10
The Element 15 is present in the bucket: 4
The Element 20 is present in the bucket: 9
```