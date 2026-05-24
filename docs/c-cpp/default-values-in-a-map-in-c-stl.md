# c++ STL 中地图的默认值

> 原文:[https://www . geesforgeks . org/default-values-in-a-map-in-c-STL/](https://www.geeksforgeeks.org/default-values-in-a-map-in-c-stl/)

**先决条件:**[STL 中的地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)
地图是用于存储键值对的容器。默认情况下，在[中，如果变量没有初始化，C/C++ 中的原始数据类型](https://www.geeksforgeeks.org/uninitialized-primitive-data-types-in-c-c/)如 **int、char、bool、float** 是未定义的，但是在映射中，当声明映射时，每个键都用默认值零进行映射。使用随机默认值初始化地图的方法如下:
**方法:**

1.  用默认值声明一个[结构](https://www.geeksforgeeks.org/structures-c/)(比如说结构**节点**)。
2.  用映射到结构节点的键初始化映射。

**语法:**

```cpp
// For Structure 
struct Node {
   int value = -1;
}

// For Map with every key mapped to default value -1
Map < int, Node > M; 
```

下图是带有默认值 **-1** :
的地图

## CPP14

```cpp
// C++ program to illustrate a Map
// initialize with default value
#include <bits/stdc++.h>
using namespace std;

// Structure Node
struct Node {
    int value = -1;
};

// Driver Code
int main()
{
    // Map initialize with key value
    // pair with each pair mapped with
    // structure Node
    map<int, Node> Map;

    // Print the default value of 1
    // store in Map
    cout << Map[1].value << endl;

    return 0;
}
```

**Output:** 

```cpp
-1
```