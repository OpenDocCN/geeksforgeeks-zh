# c++ 中的转发列表和对列表，示例

> 原文:[https://www . geesforgeks . org/转发列表和带示例 c 对列表/](https://www.geeksforgeeks.org/forward-list-and-list-of-pairs-in-c-with-examples/)

**<u>转发列表</u>**

[**<u>正向列表</u>**](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) 在 STL 中实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它与列表的不同之处在于，转发列表只跟踪下一个元素的位置，而列表同时跟踪下一个和上一个元素，因此增加了存储每个元素所需的存储空间。向前列表的缺点是不能向后迭代，并且不能直接访问它的单个元素。当只需要向前遍历时，向前列表优于列表(与单链表优于双链表相同)，因为我们可以节省空间。一些例子是，散列中的链接，图的邻接表表示等。

与转发列表一起使用的功能:

*   **push_front():** 此功能用于将元素插入到正向列表的第一个位置。该函数的值被复制到容器中第一个元素之前的空间。转发列表的大小增加 1。
*   **pop_front():** 此功能用于删除列表的第一个元素。

**<u>列表</u>**

[**<u>列表</u>**](https://www.geeksforgeeks.org/list-cpp-stl/) 是允许非连续内存分配的序列容器。与 vector 相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。通常，当我们说一个列表时，我们说的是一个双重链表。为了实现单链表，我们使用了一个转发列表。

与列表一起使用的功能:

*   **front():** 返回列表中第一个元素的值。
*   **back():** 返回列表中最后一个元素的值。
*   **push_front(x):** 在列表的开头添加一个新元素‘x’。
*   **push_back(x):** 在列表末尾添加新元素‘x’。

**<u>配对</u>**

一个 [**<u>对</u>**](https://www.geeksforgeeks.org/pair-in-cpp-stl/) 容器是一个简单的容器，在由两个数据元素或对象组成的<实用工具>头中定义。在一对中，第一个对象以“第一”引用，第二个对象以“第二”引用，顺序固定为{第一，第二}。

**语法 1:**

> **forward_list <对< data_type1，data _ type 2>T5【forward list；**
> 
> 这里
> **data _ type 1****data _ type 2**为数据类型。
> 声明的转发列表可以将对存储为仅由这些数据类型组成的元素。

**语法 2:**

> **列表<对< data_type1，data _ type 2>T5】列表；**
> 
> 这里
> **data _ type 1****data _ type 2**为数据类型。
> 声明列表可以将对存储为仅由这些数据类型组成的元素。

**<u>转发配对列表</u>**

下面是对转发列表的实现:

**例 1:**

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print forward 
// list elements
void print(forward_list<pair<int, int> >& 
           forwardListOfPairs)
{

  cout << "Forward List : " << '\n';
  for (auto currentPair : forwardListOfPairs) 
  {
    // Each element of the forwarList is
    // a pair itself
    pair<int, int> currentpair = currentPair;

    cout << "[ ";

    // Printing pair contents
    cout << currentPair.first << ' ' << 
            currentPair.second;
    cout << ']';
    cout << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a forward list of pairs
  forward_list<pair<int, int> > 
  forwardListOfPairs;

  // Declaring a pair
  pair<int, int> pair1;

  // Initializing the
  // pair
  pair1 = make_pair(11, 22);

  // Push the pair at the back
  // in the forward list
  forwardListOfPairs.push_front(pair1);

  // Declaring another pair
  pair<int, int> pair2;

  // Initializing the
  // pair
  pair2 = make_pair(33, 44);

  // Push the pair at the front
  // in the forward list
  forwardListOfPairs.push_front(pair2);

  // Declaring another pair
  pair<int, int> pair3;

  // Initializing the pair
  pair3 = make_pair(55, 66);

  // Push the pair at the front
  // in the forward list
  forwardListOfPairs.push_front(pair3);

  // Declaring another pair
  pair<int, int> pair4;

  // Initializing the pair
  pair4 = make_pair(77, 88);

  // Push the pair at the front
  // in the forward list
  forwardListOfPairs.push_front(pair4);

  // Calling print function
  print(forwardListOfPairs);
  return 0;
}
```

**Output**

```cpp
Forward List : 
[ 77 88]
[ 55 66]
[ 33 44]
[ 11 22]
```

**例 2:**

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print list
// contents
void print(forward_list<pair<int, string> >& 
           forwardListOfPairs)
{
  cout << "Forward List : " << '\n';

  for (auto currentPair : forwardListOfPairs) 
  {
    // Each element of the forward list is
    // a pair itself
    pair<int, string> currentpair = currentPair;

    cout << "[ ";

    // Printing pair elements
    cout << "First: " << currentPair.first << 
            " and " << "Second: " << 
            currentPair.second;
    cout << ']';
    cout << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a forward list of pairs
  forward_list<pair<int, string> > 
  forwardListOfPairs;

  // Declaring a pair
  pair<int, string> pair1;

  // Initializing the
  // pair
  pair1 = make_pair(1, "Geeks");

  // Push the pair at the back
  // in the forwarList
  forwardListOfPairs.push_front(pair1);

  // Declaring another pair
  pair<int, string> pair2;

  // Initializing the
  // pair
  pair2 = make_pair(2, "for");

  // Push the pair at the front
  // in the forward list
  forwardListOfPairs.push_front(pair2);

  // Declaring another pair
  pair<int, string> pair3;

  // Initializing the pair
  pair3 = make_pair(3, "Geeks");

  // Push the pair at the front
  // in the forwarList
  forwardListOfPairs.push_front(pair3);

  // Declaring another pair
  pair<int, string> pair4;

  // Initializing the pair
  pair4 = make_pair(4, "C++");

  // Push the pair at the front
  // in the forwarList
  forwardListOfPairs.push_front(pair4);

  // Calling print function
  print(forwardListOfPairs);
  return 0;
}
```

**Output**

```cpp
Forward List : 
[ First: 4 and Second: C++ ]
[ First: 3 and Second: Geeks]
[ First: 2 and Second: for]
[ First: 1 and Second: Geeks]
```

**<u>配对列表</u>**

下面是配对列表的实现:

**例 1:**

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print list
// contents
void print(list<pair<int, int> >& 
           listOfPairs)
{

  cout << "List : " << '\n';

  for (auto currentPair : listOfPairs) 
  {
    // Each element of the list is
    // a pair itself
    pair<int, int> currentpair = currentPair;

    cout << "[ ";

    // Printing pair elements
    cout << "First: " << currentPair.first << 
            " and " << "Second: " << 
            currentPair.second;
    cout << ']';
    cout << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a list of pairs
  list<pair<int, int> > listOfPairs;

  // Declaring a pair
  pair<int, int> pair1;

  // Initializing the
  // pair
  pair1 = make_pair(11, 22);

  // Push the pair at the back
  // in the list
  listOfPairs.push_back(pair1);

  // Declaring another pair
  pair<int, int> pair2;

  // Initializing the
  // pair
  pair2 = make_pair(33, 44);

  // Push the pair at the back
  // in the list
  listOfPairs.push_back(pair2);

  // Declaring another pair
  pair<int, int> pair3;

  // Initializing the pair
  pair3 = make_pair(55, 66);

  // Push the pair at the front
  // in the list
  listOfPairs.push_front(pair3);

  // Declaring another pair
  pair<int, int> pair4;

  // Initializing the pair
  pair4 = make_pair(77, 88);

  // Push the pair at the back
  // in the list
  listOfPairs.push_back(pair4);

  // Calling print function
  print(listOfPairs);
  return 0;
}
```

**Output**

```cpp
List : 
[ First: 55 and Second: 66]
[ First: 11 and Second: 22]
[ First: 33 and Second: 44]
[ First: 77 and Second: 88]
```

**例 2:**

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print list
// contents
void print(list<pair<int, string> >& 
           listOfPairs)
{

  cout << "List : " << '\n';
  for (auto currentPair : listOfPairs) 
  {
    // Each element of the forwarList is
    // a pair itself
    pair<int, string> currentpair = currentPair;

    cout << "[ ";

    // Printing pair contents
    cout << "First: " << currentPair.first << 
            " and " << "Second: " << 
            currentPair.second;
    cout << ']';
    cout << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a list of pairs
  list<pair<int, string> > listOfPairs;

  // Declaring a pair
  pair<int, string> pair1;

  // Initializing the
  // pair
  pair1 = make_pair(1, "Geeks");

  // Push the pair at the back
  // in the list
  listOfPairs.push_front(pair1);

  // Declaring another pair
  pair<int, string> pair2;

  // Initializing the
  // pair
  pair2 = make_pair(2, "for");

  // Push the pair at the front
  // in the list
  listOfPairs.push_front(pair2);

  // Declaring another pair
  pair<int, string> pair3;

  // Initializing the pair
  pair3 = make_pair(3, "Geeks");

  // Push the pair at the front
  // in the list
  listOfPairs.push_front(pair3);

  // Declaring another pair
  pair<int, string> pair4;

  // Initializing the pair
  pair4 = make_pair(4, "C++");

  // Push the pair at the front
  // in the list
  listOfPairs.push_front(pair4);

  // Calling print function
  print(listOfPairs);
  return 0;
}
```

**Output**

```cpp
List : 
[ First: 4 and Second: C++ ]
[ First: 3 and Second: Geeks]
[ First: 2 and Second: for]
[ First: 1 and Second: Geeks]
```