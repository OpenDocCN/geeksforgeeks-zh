# C++ STL 中无序多集 max_size

> 原文：[https://www.geeksforgeeks.org/unordered_multiset-max_size-in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-max_size-in-c-stl/)

## 描述
`无序多集`的`max_size()`函数返回该容器因系统限制所能容纳的最大元素数量，或者说受控序列的最大大小。

## 语法
```cpp
size_type max_size() const;
```
其中`size_type`为无符号整型。

## 返回值
成员函数返回对象可以容纳的最长序列的长度。总之，元素的最大数量。

## 示例
下面的程序说明了`无序多集`的`max_size()`函数：

**例 1:**
```cpp
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

// Define the unordered_set
    unordered_multiset<int> num{ 1, 2, 3, 4, 5, 6 };

cout << "Maximum size = "
         << num.max_size() << "\n";

cout << "Current size = "
         << num.size();

return 0;
}
```

**输出：**
```cpp
Maximum size = 1152921504606846975
Current size = 6
```

## 复杂度
执行一个操作需要常数时间复杂度，即`O(1)`。