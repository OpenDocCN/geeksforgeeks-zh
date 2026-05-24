# c++ 中地图的向量，带示例

> 原文:[https://www . geeksforgeeks . org/vector-of-map-in-c-with-examples/](https://www.geeksforgeeks.org/vector-of-maps-in-c-with-examples/)

[**STL 中的地图**](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) **:** 地图是以映射方式存储元素的[关联容器](https://www.geeksforgeeks.org/sequence-vs-associative-containers-cpp/)。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

[**STL 中的 Vector:**](https://www.geeksforgeeks.org/vector-in-cpp-stl/)[Vector](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。向量元素被放在连续的存储中，这样就可以使用迭代器访问和遍历它们。

[](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)****中的**矢量地图:**矢量地图可以用来设计复杂高效的数据结构。****

****语法:****

> ****有序地图矢量:**
> 矢量<地图<数据类型，数据类型>>VM；**
> 
> ****无序地图矢量:**
> 矢量<无序 _ 地图<数据类型，数据类型>>VUM；**

****例:**
给了一根弦。任务是找到每个索引的字符频率。**

## **C++ 14**

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
    vector<map<char, int> > mp(s.length());

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

****Output:** 

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
```**