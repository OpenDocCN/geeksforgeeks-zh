# C++ STL 中的 unordered_multiset::bucket() 函数

> 原文：[https://www.geeksforgeeks.org/unordered_multiset-bucket-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-bucket-function-in-c-stl/)

## 函数介绍

`unordered_multiset::bucket()` 是 C++ STL 中的内置函数，返回给定元素所在的桶编号。桶编号的范围从 0 到 `bucket_count()-1`。

## 语法

```cpp
unordered_multiset_name.bucket(element)
```

## 参数

该函数接受单个强制参数 `element`，该参数指定要返回其桶编号的值。

## 返回值

返回无符号整数类型，表示元素所在的桶号。

## 示例程序

以下程序说明了上述功能：

### 程序 1

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

// declaration
    unordered_multiset<int> sample;

// inserts element
    sample.insert(10);
    sample.insert(15);
    sample.insert(15);
    sample.insert(13);
    sample.insert(13);

for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "The bucket number in which " << *it
             << " is " << sample.bucket(*it) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket number in which 13 is 6
The bucket number in which 13 is 6
The bucket number in which 10 is 3
The bucket number in which 15 is 1
The bucket number in which 15 is 1
```

### 程序 2

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

// declaration
    unordered_multiset<char> sample;

// inserts element
    sample.insert('a');
    sample.insert('a');
    sample.insert('b');
    sample.insert('b');
    sample.insert('c');
    sample.insert('c');
    sample.insert('e');

for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "The bucket number in which " << *it
             << " is " << sample.bucket(*it) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket number in which e is 16
The bucket number in which a is 12
The bucket number in which a is 12
The bucket number in which b is 13
The bucket number in which b is 13
The bucket number in which c is 14
The bucket number in which c is 14
```