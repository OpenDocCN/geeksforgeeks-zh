# c++ 中的正向列表和无序映射列表示例

> 原文:[https://www . geeksforgeeks . org/forward-list-and-list-of-ordered-map-in-c-with-examples/](https://www.geeksforgeeks.org/forward-list-and-list-of-unordered-maps-in-c-with-examples/)

**<u>转发列表</u>**

[**<u>正向列表</u>**](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) 在 STL 中实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它与列表的不同之处在于，转发列表只跟踪下一个元素的位置，而列表同时跟踪下一个和上一个元素，因此增加了存储每个元素所需的存储空间。向前列表的缺点是不能向后迭代，并且不能直接访问它的单个元素。当只需要向前遍历时，向前列表优于列表(与单链表优于双链表相同)，因为我们可以节省空间。一些例子是，散列中的链接，图的邻接表表示等。

**与转发列表一起使用的功能:**

*   **push_front(x):** 在前向列表的开头添加新元素‘x’。
*   **pop_front():** 此功能用于删除转发列表的第一个元素。

**<u>列表</u>**

[**<u>列表</u>**](https://www.geeksforgeeks.org/list-cpp-stl/) 是允许非连续内存分配的序列容器。与 vector 相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。通常，当我们说一个列表时，我们说的是一个双重链表。为了实现单链表，我们使用了一个转发列表。

**列表使用的功能:**

*   **front():** 返回列表中第一个元素的值。
*   **back():** 返回列表中最后一个元素的值。
*   **push_front(x):** 在列表的开头添加一个新元素‘x’。
*   **push_back(x):** 在列表末尾添加新元素‘x’。

**<u>无序 _ 地图</u>**

[](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/)<u>无序映射是一个关联容器，用于存储键值和映射值组合而成的元素。键值用于唯一标识元素，映射值是与键相关联的内容。键和值都可以是预定义或用户定义的任何类型。内部使用 [**<u>哈希表</u>**](https://www.geeksforgeeks.org/hashing-set-1-introduction/) 实现无序映射。</u>

<u>**无序地图使用的函数:**</u>

*   <u>**at():**c++ 无序 _map 中的这个函数返回对以元素为键 k 的值的引用。</u>
*   <u>**begin():** 返回一个迭代器，指向无序映射容器中容器的第一个元素</u>
*   <u>**end():** 返回一个迭代器，该迭代器指向无序映射容器中容器中最后一个元素之后的位置</u>
*   <u>**size():** 返回无序地图中存在的元素数量。</u>

<u>本文主要讨论如何在 C++ 中使用正向列表和无序映射列表。在设计复杂数据结构时，列表向量和转发列表非常有用。</u>

<u>**<u>【无序地图转发列表】</u>**</u>

<u>下面是使用无序映射正向列表的实现:</u>

<u>**例 1:**</u>

## <u>C++ </u>

```cpp
// C++ program to implement
// the above concept
#include <bits/stdc++.h>
using namespace std;

// Function to print forward 
// list elements
void print(forward_list<unordered_map<int, int> >& 
           forwardList1)
{
  cout << "Forward List : \n";

  for (auto currentUnorderedMap : forwardList1) 
  {
    // Each element of the forward_list 
    // is a unordered map

    cout << "Unordered Map : ";
    cout << "[   ";

    // Print unordered map elements
    for (auto it = currentUnorderedMap.begin();
              it != currentUnorderedMap.end(); it++) 
    {
      cout << "First : " << it->first << " , " << 
              "Second : " << it->second << "   ";
    }
    cout << "]\n";
  }
}

// Driver code
int main()
{
  // Declaring a forward list of 
  // unordered maps
  forward_list<unordered_map<int, int> > 
  forwardList1;

  // Declaring a unordered map
  unordered_map<int, int> unorderedMap1;

  // Hashing values
  unorderedMap1[2] = 4;
  unorderedMap1[4] = 3;
  unorderedMap1[6] = 9;

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap1);

  // Declaring another unordered map
  unordered_map<int, int> unorderedMap2;

  // Hashing values
  unorderedMap2[31] = 8;
  unorderedMap2[11] = 3;
  unorderedMap2[23] = 7;

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap2);

  // Declaring another unordered map
  unordered_map<int, int> unorderedMap3;

  // Hashing values
  unorderedMap3[7] = 3;
  unorderedMap3[18] = 1;
  unorderedMap3[9] = 6;

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap3);

  // Declaring another unordered map
  unordered_map<int, int> unorderedMap4;

  // Hashing values
  unorderedMap4[32] = 9;
  unorderedMap4[15] = 3;
  unorderedMap4[97] = 5;

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap4);

  print(forwardList1);
  return 0;
}
```

<u>**输出:**</u>

> <u>转发列表:
> 无序地图:【第一:97，第二:5 第一:32，第二:9 第一:15，第二:3】
> 无序地图:【第一:9，第二:6 第一:7，第二:3 第一:18，第二:1】
> 无序地图:【第一:23，第二:7 第一:31，第二:8 第一:11， 第二:3 ]
> 无序地图:[第一:6，第二:9 第一:2，第二:4 第一:4，第二:3 ]</u>

<u>**例 2:**</u>

## <u>C++ </u>

```cpp
// C++ program to implement
// the above concept
#include <bits/stdc++.h>
using namespace std;

// Function to print forward 
// list elements
void print(forward_list<unordered_map<int, string> >& 
           forwardList1)
{
  cout << "Forward List : \n";

  for (auto currentUnorderedMap : forwardList1)
  {
    // Each element of the forward list is 
    // a unordered map

    cout << "Unordered Map : ";
    cout << "[   ";

    // Print unordered map elements
    for (auto it = currentUnorderedMap.begin();
              it != currentUnorderedMap.end(); it++) 
    {
      cout << "First : " << it->first << " , " << 
              "Second : " << it->second << "   ";
    }
    cout << "]\n";
  }
}

// Driver code
int main()
{
  // Declaring a forward_list of 
  // unordered maps
  forward_list<unordered_map<int, string> > 
  forwardList1;

  // Declaring a unordered map
  unordered_map<int, string> unorderedMap1;

  // Hashing values
  unorderedMap1[2] = "Geeks";
  unorderedMap1[4] = "for";
  unorderedMap1[6] = "Geeks";

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap1);

  // Declaring another unordered map
  unordered_map<int, string> unorderedMap2;

  // Hashing values
  unorderedMap2[3] = "Python";
  unorderedMap2[11] = "Java";
  unorderedMap2[23] = "C++";

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap2);

  // Declaring another unordered map
  unordered_map<int, string> unorderedMap3;

  // Hashing values
  unorderedMap3[7] = "C";
  unorderedMap3[18] = "PHP";
  unorderedMap3[9] = "Swift";

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap3);

  // Declaring another unordered map
  unordered_map<int, string> unorderedMap4;

  // Hashing values
  unorderedMap4[121] = "Hello";
  unorderedMap4[97] = "Coding";
  unorderedMap4[197] = "World";

  // Push back the unordered map in 
  // the forward list
  forwardList1.push_front(unorderedMap4);

  print(forwardList1);
  return 0;
}
```

<u>**输出:**</u>

> <u>转发列表:
> 无序地图:【第一:197，第二:世界第一:121，第二:你好第一:97，第二:编码】
> 无序地图:【第一:9，第二:Swift 第一:7，第二:C 第一:18，第二:PHP】
> 无序地图:【第一:23，第二:C++ 第一:3，第二:Python 第一:11， 第二:Java ]
> 无序地图:【第一:6，第二:极客第一:2，第二:极客第一:4，第二:for】</u>

<u>**<u>无序地图列表</u>**</u>

<u>下面是使用无序映射列表的实现:</u>

#### <u>**例 1:**</u>

## <u>C++ </u>

```cpp
// C++ program to implement
// the above concept
#include <bits/stdc++.h>
using namespace std;

// Function to print list elements
void print(list<unordered_map<int, int> >& 
           List)
{
  cout << "List : \n";
  for (auto currentUnorderedMap : List) 
  {
    // Each element of the list is 
    // a unordered map
    cout << "Unordered Map : ";
    cout << "[   ";

    // Print unordered map elements
    for (auto it = currentUnorderedMap.begin();
              it != currentUnorderedMap.end(); it++) 
    {
      cout << "First : " << it->first << " , " << 
              "Second : " << it->second << "   ";
    }
    cout << "]\n";
  }
}

// Driver code
int main()
{
  // Declaring a list of unordered maps
  list<unordered_map<int, int> > List;

  // Declaring a unordered map
  unordered_map<int, int> unorderedMap1;

  // Hashing values
  unorderedMap1[2] = 4;
  unorderedMap1[4] = 3;
  unorderedMap1[6] = 9;

  // Push back the unordered map 
  // in the list
  List.push_front(unorderedMap1);

  // Declaring another unordered map
  unordered_map<int, int> unorderedMap2;

  // Hashing values
  unorderedMap2[31] = 8;
  unorderedMap2[11] = 3;
  unorderedMap2[23] = 7;

  // Push back the unordered map 
  // in the list
  List.push_front(unorderedMap2);

  // Declaring another unordered map
  unordered_map<int, int> unorderedMap3;

  // Hashing values
  unorderedMap3[7] = 3;
  unorderedMap3[18] = 1;
  unorderedMap3[9] = 6;

  // Push back the unordered map 
  // in the list
  List.push_front(unorderedMap3);

  // Declaring another unordered map
  unordered_map<int, int> unorderedMap4;

  // Hashing values
  unorderedMap4[32] = 9;
  unorderedMap4[15] = 3;
  unorderedMap4[97] = 5;

  // Push back the unordered map 
  // in the list
  List.push_front(unorderedMap4);

  print(List);
  return 0;
}
```

<u>**输出:**</u>

> <u>列表:
> 无序地图:【第一:97，第二:5 第一:32，第二:9 第一:15，第二:3】
> 无序地图:【第一:9，第二:6 第一:7，第二:3 第一:18，第二:1】
> 无序地图:【第一:23，第二:7 第一:31，第二:8 第一:11， 第二:3 ]
> 无序地图:[第一:6，第二:9 第一:2，第二:4 第一:4，第二:3 ]</u>

<u>**例 2:**</u>

## <u>C++ </u>

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print list elements
void print(list<unordered_map<int, string> >& List)
{
  cout << "List : \n";
  for (auto currentUnorderedMap : List) 
  {
    // Each element of the list is 
    // a unordered map
    cout << "Unordered Map : ";
    cout << "[   ";

    // Print unordered map elements
    for (auto it = currentUnorderedMap.begin();
              it != currentUnorderedMap.end(); it++) 
    {
      cout << "First : " << it->first << " , " << 
              "Second : " << it->second << "   ";
    }
    cout << "]\n";
  }
}

// Driver code
int main()
{
  // Declaring a list of unordered maps
  list<unordered_map<int, string> > List;

  // Declaring a unordered map
  unordered_map<int, string> unorderedMap1;

  // Hashing values
  unorderedMap1[2] = "Geeks";
  unorderedMap1[4] = "for";
  unorderedMap1[6] = "Geeks";

  // Push back the unordered map in 
  // the forward list
  List.push_front(unorderedMap1);

  // Declaring another unordered map
  unordered_map<int, string> unorderedMap2;

  // Hashing values
  unorderedMap2[3] = "Python";
  unorderedMap2[11] = "Java";
  unorderedMap2[23] = "C++";

  // Push back the unordered map in 
  // the forward list
  List.push_front(unorderedMap2);

  // Declaring another unordered map
  unordered_map<int, string> unorderedMap3;

  // Hashing values
  unorderedMap3[7] = "C";
  unorderedMap3[18] = "PHP";
  unorderedMap3[9] = "Swift";

  // Push back the unordered map in 
  // the forward list
  List.push_front(unorderedMap3);

  // Declaring another unordered map
  unordered_map<int, string> unorderedMap4;

  // Hashing values
  unorderedMap4[121] = "Hello";
  unorderedMap4[97] = "Coding";
  unorderedMap4[197] = "World";

  // Push back the unordered map in 
  // the forward list
  List.push_front(unorderedMap4);

  print(List);
  return 0;
}
```

<u>**输出:**</u>

> <u>列表:
> 无序地图:【第一:197，第二:世界第一:121，第二:你好第一:97，第二:编码】
> 无序地图:【第一:9，第二:Swift 第一:7，第二:C 第一:18，第二:PHP】
> 无序地图:【第一:23，第二:C++ 第一:3，第二:Python 第一:11， 第二:Java ]
> 无序地图:【第一:6，第二:极客第一:2，第二:极客第一:4，第二:for】</u>