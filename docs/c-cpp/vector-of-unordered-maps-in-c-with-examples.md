# c++ 中无序映射的向量及示例

> 原文:[https://www . geeksforgeeks . org/无序地图矢量 c-in-with-examples/](https://www.geeksforgeeks.org/vector-of-unordered-maps-in-c-with-examples/)

**矢量**:

[**向量**](https://www.geeksforgeeks.org/vector-in-cpp-stl/) :与**动态**数组相同，当一个元素被**插入**或**删除**时，能够自动**调整**本身的大小，其存储由容器自动处理。向量元素被放置在**连续的**存储器中，这样就可以使用迭代器访问和遍历它们。

向量使用的一些函数:

*   [**begin()**](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/) **:** 它返回一个指向向量中第一个元素的迭代器
*   [**end()**](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/) **:** 它返回一个迭代器，指向向量中最后一个元素之后的理论元素
*   [**size()**](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) **:返回向量中元素的个数。**

**无序地图:**

[**<u>【无序 _ 映射】</u>**](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/) 是一个关联容器，存储键值和映射值组合而成的元素。键值用于唯一标识元素，映射值是与键相关联的内容。键和值都可以是预定义或用户定义的任何类型。无序地图中的元素不以任何特定顺序排列。内部使用 [**<u>哈希表</u>**](https://www.geeksforgeeks.org/hashing-set-1-introduction/) 实现无序映射。

无序映射使用的一些函数:

*   **at():**c++ 无序 _map 中的这个函数返回对以元素为键 k 的值的引用。
*   **begin():** 返回一个迭代器，指向无序映射容器中容器的第一个元素
*   **end():** 返回一个迭代器，该迭代器指向无序映射容器中容器中最后一个元素之后的位置

本文主要讨论无序地图的**向量**如何在 C++ 中使用。无序地图的矢量在设计复杂的数据结构时非常有用。

下面是使用无序映射向量的实现:

**例 1:**

## C++

```cpp
// C++ program to illustrate the working
// of vector of unordered maps
#include <bits/stdc++.h>
using namespace std;

// Function to print vector elements
void print(vector<unordered_map<int, int> >& vect)
{

    cout << "vector : \n";
    for (int i = 0; i < (int)vect.size(); i++) {

        // Each element of the vector is a unordered map
        unordered_map<int, int> unorderedMap = vect[i];

        cout << "unordered map : ";
        cout << "[  ";

        // Print unordered map elements
        for (auto it = unorderedMap.begin();
             it != unorderedMap.end(); it++) {
            cout << it->first << ':' << it->second << "  ";
        }

        cout << "]\n";
    }
}

// Driver Code
int main()
{

    // Declaring a vector of unordered maps
    vector<unordered_map<int, int> > vect;

    // Declaring a unordered map
    unordered_map<int, int> unorderedMap1;

    // Hashing values
    unorderedMap1[2] = 1;
    unorderedMap1[4] = 7;
    unorderedMap1[6] = 10;

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap1);

    // Declaring another unordered map
    unordered_map<int, int> unorderedMap2;

    // Hashing values
    unorderedMap2[14] = 11;
    unorderedMap2[15] = 21;
    unorderedMap2[6] = 34;

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap2);

    // Declaring another unordered map
    unordered_map<int, int> unorderedMap3;

    // Hashing values
    unorderedMap3[7] = 277;
    unorderedMap3[18] = 188;
    unorderedMap3[9] = 399;
    // Push back the unordered map in the vector
    vect.push_back(unorderedMap3);

    // Declaring another unordered map
    unordered_map<int, int> unorderedMap4;

    // Hashing values
    unorderedMap4[121] = 88;
    unorderedMap4[97] = 99;
    unorderedMap4[197] = 199;

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap4);

    print(vect);
    return 0;
}
```

**Output**

```cpp
vector : 
unordered map : [  6:10  2:1  4:7  ]
unordered map : [  6:34  14:11  15:21  ]
unordered map : [  9:399  7:277  18:188  ]
unordered map : [  197:199  121:88  97:99  ]
```

**例 2:**

## C++

```cpp
// C++ program to illustrate the working
// of vector of unordered maps
#include <bits/stdc++.h>
using namespace std;

// Function to print vector elements
void print(vector<unordered_map<int, string> >& vect)
{

    cout << "vector : \n";
    for (int i = 0; i < (int)vect.size(); i++) {
        // Each element of the vector is a unordered map
        unordered_map<int, string> unorderedMap = vect[i];

        cout << "unordered map : ";
        cout << "[  ";

        // Print unordered map elements
        for (auto it = unorderedMap.begin();
             it != unorderedMap.end(); it++) {
            cout << it->first << ':' << it->second << "  ";
        }

        cout << "]\n";
    }
}

// Driver Code
int main()
{

    // Declaring a vector of unordered maps
    vector<unordered_map<int, string> > vect;

    // Declaring a unordered map
    unordered_map<int, string> unorderedMap1;

    // Hashing values
    unorderedMap1[11] = "Geeks";
    unorderedMap1[23] = "for";
    unorderedMap1[32] = "Geeks";

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap1);

    // Declaring another unordered map
    unordered_map<int, string> unorderedMap2;

    // Hashing values
    unorderedMap2[12] = "Python";
    unorderedMap2[32] = "Java";
    unorderedMap2[73] = "C++";

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap2);

    // Declaring another unordered map
    unordered_map<int, string> unorderedMap3;

    // Hashing values
    unorderedMap3[11] = "PHP";
    unorderedMap3[2] = "C#";
    unorderedMap3[35] = "Assembly";
    // Push back the unordered map in the vector
    vect.push_back(unorderedMap3);

    // Declaring another unordered map
    unordered_map<int, string> unorderedMap4;

    // Hashing values
    unorderedMap4[14] = "C";
    unorderedMap4[27] = "Javascript";
    unorderedMap4[54] = "Swift";

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap4);

    print(vect);
    return 0;
}
```

**Output**

```cpp
vector : 
unordered map : [  32:Geeks  11:Geeks  23:for  ]
unordered map : [  73:C++  12:Python  32:Java  ]
unordered map : [  35:Assembly  11:PHP  2:C#  ]
unordered map : [  54:Swift  14:C  27:Javascript  ]
```

**例 3:**

## C++

```cpp
// C++ program to illustrate the working
// of vector of unordered maps
#include <bits/stdc++.h>
using namespace std;

// Function to print vector elements
void print(vector<unordered_map<int, char> >& vect)
{

    cout << "vector : \n";
    for (int i = 0; i < (int)vect.size(); i++) {
        // Each element of the vector is a unordered map
        unordered_map<int, char> unorderedMap = vect[i];

        cout << "unordered map : ";
        cout << "[  ";

        // Print unordered map elements
        for (auto it = unorderedMap.begin();
             it != unorderedMap.end(); it++) {
            cout << it->first << ':' << it->second << "  ";
        }

        cout << "]\n";
    }
}

// Driver Code
int main()
{

    // Declaring a vector of unordered maps
    vector<unordered_map<int, char> > vect;

    // Declaring a unordered map
    unordered_map<int, char> unorderedMap1;

    // Hashing values
    unorderedMap1[2] = 'G';
    unorderedMap1[7] = 'e';
    unorderedMap1[12] = 'e';
    unorderedMap1[14] = 'k';
    unorderedMap1[21] = 's';

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap1);

    // Declaring another unordered map
    unordered_map<int, char> unorderedMap2;

    // Hashing values
    unorderedMap2[13] = 'J';
    unorderedMap2[15] = 'a';
    unorderedMap2[24] = 'v';
    unorderedMap2[27] = 'a';

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap2);

    // Declaring another unordered map
    unordered_map<int, char> unorderedMap3;

    // Hashing values
    unorderedMap3[33] = 'P';
    unorderedMap3[37] = 'y';
    unorderedMap3[41] = 't';
    unorderedMap3[19] = 'h';
    unorderedMap3[43] = 'o';
    unorderedMap3[53] = 'o';

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap3);

    // Declaring another unordered map
    unordered_map<int, char> unorderedMap4;

    // Hashing values
    unorderedMap4[15] = 's';
    unorderedMap4[53] = 'w';
    unorderedMap4[16] = 'i';
    unorderedMap4[23] = 'f';
    unorderedMap4[27] = 't';

    // Push back the unordered map in the vector
    vect.push_back(unorderedMap4);

    print(vect);
    return 0;
}
```

**Output**

```cpp
vector : 
unordered map : [  12:e  2:G  21:s  14:k  7:e  ]
unordered map : [  24:v  27:a  13:J  15:a  ]
unordered map : [  53:o  43:o  41:t  19:h  33:P  37:y  ]
unordered map : [  27:t  23:f  16:i  15:s  53:w  ]
```