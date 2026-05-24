# C++ 中 vector of maps 的用法与示例

> 原文：[https://www.geeksforgeeks.org/vector-of-maps-in-c-with-examples/](https://www.geeksforgeeks.org/vector-of-maps-in-c-with-examples/)

## STL 中的 map

`map` 是以键值对方式存储元素的[关联容器](https://www.geeksforgeeks.org/sequence-vs-associative-containers-cpp/)。每个元素都有一个键（key）和一个映射值（mapped value）。容器中不允许存在键值相同的两个元素。

## STL 中的 vector

[`vector`](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 与[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)相同，能够在插入或删除元素时自动调整自身大小，其存储空间由容器自动管理。向量元素在内存中连续存储，因此可以使用迭代器进行访问和遍历。

## vector of maps

`vector` 和 `map` 的组合可以用来设计复杂且高效的数据结构。

### 语法

有序 `map` 的 `vector`：
```cpp
vector<map<DataType, DataType>> VM;
```

无序 `map` 的 `vector`：
```cpp
vector<unordered_map<DataType, DataType>> VUM;
```

### 示例

给定一个字符串，任务是找出每个索引位置之前（包含该位置）所有字符的频率。

```cpp
// C++ program to demonstrate the use
// of vector of maps
#include <bits/stdc++.h>
using namespace std;

// Function to count frequency
// up to each index
void findOccurences(string s)
{
    // Vector of map
    vector<map<char, int>> mp(s.length());

    // Traverse the string s
    for (int i = 0; i < s.length(); i++) {

        // Update the frequency
        for (int j = 0; j <= i; j++) {
            mp[i][s[j]]++ ;
        }
    }

    // Print the vector of map
    for (int i = 0; i < s.length(); i++) {

        cout << "Frequency upto "
             << "position " << i + 1
             << endl;

        // Traverse the map
        for (auto x : mp[i])
            cout << x.first << "-"
                 << x.second << endl;
    }
}

// Driver Code
int main()
{
    // Input string S
    string S = "geeks";

    // Function Call
    findOccurences(S);

    return 0;
}
```

**输出：**

```cpp
Frequency upto position 1
g-1
Frequency upto position 2
e-1
g-1
Frequency upto position 3
e-2
g-1
Frequency upto position 4
e-2
g-1
k-1
Frequency upto position 5
e-2
g-1
k-1
s-1
```