# c++ 中元组集，示例

> 原文:[https://www . geeksforgeeks . org/带示例的 c 元组集/](https://www.geeksforgeeks.org/set-of-tuples-in-c-with-examples/)

**什么是元组？**
一个 [<u>元组</u>](https://www.geeksforgeeks.org/tuples-in-c/#:~:text=A%20tuple%20is%20an%20object,which%20they%20will%20be%20accessed.) 是一个可以容纳多个元素的对象。元素可以是不同的数据类型。元组的元素按照被访问的顺序被初始化为参数。

**元组上的操作:**
**1。get():** get()用于访问元组值并修改它们，它接受索引和元组名称作为参数来访问特定的元组元素。
**2。make_tuple():** make_tuple()用于给 tuple 赋值。传递的值应该与元组中声明的值保持一致。

**什么是集合？**
[<u>集合</u>](https://www.geeksforgeeks.org/set-in-cpp-stl/) 是一种关联的容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

与 Set 相关的一些基本功能:
**1。**[**<u>begin()</u>**](https://www.geeksforgeeks.org/setbegin-setend-c-stl/)**:**返回集合中第一个元素的迭代器。
**2。**[**<u>end()</u>**](https://www.geeksforgeeks.org/setbegin-setend-c-stl/)**:**返回集合中最后一个元素之后的理论元素的迭代器。
**3。**[**<u>size()</u>**](https://www.geeksforgeeks.org/setsize-c-stl/)**:返回集合中元素的个数。
**4。**[**<u>max _ size()</u>:**](https://www.geeksforgeeks.org/set-max_size-function-in-c-stl/)返回集合可以容纳的最大元素数。
**5。** [**<u>空()</u>**](https://www.geeksforgeeks.org/setempty-c-stl/) **:返回集合是否为空。****

在实现复杂的数据结构时，一组元组可能非常有用。下面是实现上述方法的 C++ 程序-

## C++

```cpp
// C++ program to demonstrate the 
// implementation of set of
// tuples
#include <bits/stdc++.h>
using namespace std;

// Function to print set contents
void print(set<tuple<int, int, 
                     int> >& setOfTuples)
{
  for (auto x : setOfTuples) 
  {
    tuple<int, int, int> tp = x;
    cout << get<0>(tp) << 
            ' ' << get<1>(tp) << 
            ' ' << get<2>(tp) << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a set of tuples
  set<tuple<int, int, 
            int> > setOfTuples;

  // Initializing tuples
  tuple<int, int, 
        int> tuple1;
  tuple1 = make_tuple(1, 2, 3);

  tuple<int, int, 
        int> tuple2;
  tuple2 = make_tuple(2, 3, 5);

  tuple<int, int, 
        int> tuple3;
  tuple3 = make_tuple(2, 3, 4);

  tuple<int, int, 
        int> tuple4;
  tuple4 = make_tuple(2, 1, 4);

  tuple<int, int, 
        int> tuple5;
  tuple5 = make_tuple(5, 8, 14);

  // Inserting into set
  setOfTuples.insert(tuple1);
  setOfTuples.insert(tuple2);
  setOfTuples.insert(tuple3);
  setOfTuples.insert(tuple4);
  setOfTuples.insert(tuple5);

  // Calling print function
  print(setOfTuples);

  return 0;
}
```

**Output**

```cpp
1 2 3
2 1 4
2 3 4
2 3 5
5 8 14
```

默认情况下，元组在集合中以非降序排列，并遵循以下逻辑:
在集合中，如果两个元组的第一个值相等，则比较元组的第二个值，如果它也相等，则比较第三个值。但是总是有可能将比较器传递给集合。

下面是实现上述方法的 C++ 程序

## C++

```cpp
// C++ program to demonstrate the 
// implementation of set of tuples 
// by using custom comparator
#include <bits/stdc++.h>
using namespace std;

// Comparator for arranging elements 
// in non-ascending order We can 
// always modify the comparator as 
// per the requirement
struct cmp 
{
  bool operator()(const tuple<int, int, 
                              int>& x,
                  const tuple<int, int, 
                              int>& y)
  {

    if (get<0>(x) == get<0>(y))
    {
      if (get<1>(x) == get<1>(y))
        return get<2>(x) > get<2>(y);
      return get<1>(x) > get<1>(y);
    }

    return get<0>(x) > get<0>(y);
  }
};

// Function to print set elements
void print(set<tuple<int, int, 
                     int>, cmp>& setOfTuples)
{
  for (auto x : setOfTuples) 
  {
    tuple<int, int, int> tp = x;
    cout << get<0>(tp) << 
            ' ' << get<1>(tp) << 
            ' ' << get<2>(tp) << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a set of tuples
  set<tuple<int, int, 
            int>, cmp> setOfTuples;

  // Initializing tuples
  tuple<int, int, 
        int> tuple1;
  tuple1 = make_tuple(1, 2, 3);

  tuple<int, int, 
        int> tuple2;
  tuple2 = make_tuple(2, 3, 5);

  tuple<int, int, 
        int> tuple3;
  tuple3 = make_tuple(2, 3, 4);

  tuple<int, int, 
        int> tuple4;
  tuple4 = make_tuple(2, 1, 4);

  tuple<int, int, 
        int> tuple5;
  tuple5 = make_tuple(5, 8, 14);

  // Inserting into set
  setOfTuples.insert(tuple1);
  setOfTuples.insert(tuple2);
  setOfTuples.insert(tuple3);
  setOfTuples.insert(tuple4);
  setOfTuples.insert(tuple5);

  // Calling print function
  print(setOfTuples);

  return 0;
}
```

**Output**

```cpp
5 8 14
2 3 5
2 3 4
2 1 4
1 2 3
```