# c++ 中元组的多集合，示例

> 原文:[https://www . geeksforgeeks . org/多元组集-in-c-with-examples/](https://www.geeksforgeeks.org/multiset-of-tuples-in-c-with-examples/)

**<u>什么是元组？</u>T3】**

[C++ ](http://www.geeksforgeeks.org/c-plus-plus/) 中的[元组](https://www.geeksforgeeks.org/tuples-in-c/)是将一组元素绑定在一起的[对象](https://www.geeksforgeeks.org/difference-between-class-and-object/)。元素可以是相似的，也可以是不同的数据类型。元组的元素按照被访问的顺序初始化。

**语法:**

> **元组<数据 _ 类型 1，数据 _ 类型 2，数据类型 3，…。>我的元组**
> 
> 这里，
> 数据类型 1，数据类型 2，数据类型 3。。。。是相似或不相似的数据类型

**与元组相关联的函数:**

**1。****make _ tuple():**make _ tuple()用于给 tuple 赋值。传递的值应该与元组中声明的值保持一致。

**语法:**

> **myTuple = make_tuple(value1，value2，value3，…。)**

**2。get():** get()用于访问元组值并修改它们，它接受索引和元组名称作为参数来访问特定的元组元素。

**语法:**

> **获取<索引> (myTuple)**
> 
> 这里，
> 索引是我们想要在 myTuple 中访问的元素的索引。元组中的索引从零开始。

**<u>什么是多集？</u>T3】**

一个[多集合](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)是一种类型的[关联容器](https://www.geeksforgeeks.org/sequence-vs-associative-containers-cpp/)，它类似于一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)，但是在一个多集合的情况下，所有的元素都必须是成对不同的。简单来说，可以有多个元素具有相同的值。

**语法:**

> **<【datatype】>mymultisect；**
> 
> 这里，
> 数据类型可以是相似或不相似的数据类型。

**与多集相关的功能:**

*   [**begin():**](https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/#:~:text=The%20multiset%3A%3Abegin(),according%20to%20the%20sorting%20criterion.) 返回多集合中第一个元素的迭代器。
*   **end():** 返回多集最后一个元素之后的理论元素的迭代器。
*   [**size()**](https://www.geeksforgeeks.org/multiset-size-in-c-stl-with-examples/) **:返回多集合中元素的个数。**
*   [**【max _ size()**](https://www.geeksforgeeks.org/multiset-max_size-in-cpp-stl-with-examples/)**:**返回多集可以容纳的最大元素数。
*   [**空()**](https://www.geeksforgeeks.org/multiset-empty-function-in-c-stl/) **:返回多集是否为空。**

当算法需要复杂的数据结构时，多元组集非常有用。本文主要讨论如何在 C++ 中创建多元组集。注意，为了简单起见，考虑了三个元素的元组，但是元组也可以包含更多或更少的元素。

**<u>多组元组</u>**

元组的多集合是其中每个元素都是元组的多集合。

**语法:**

> **多集合<元组<数据类型 1、数据类型 2、数据类型 3>T5】多集合；**
> 
> 在这里，
> 数据类型 1、数据类型 2、数据类型 3 是相似或不相似的数据类型。

**示例 1:** 下面是实现多组元组的 C++ 程序:

## C++

```cpp
// C++ program to illustrate the
// implementation of multiset of
// tuples
#include <bits/stdc++.h>
using namespace std;

// Function to print multiset contents
void print(multiset<tuple<int, int,
           int> >& multisetOfTuples)

{
  // Iterating over multisetOfTuples elements
  for (auto x : multisetOfTuples)
  {
    // Each element is a tuple itself
    tuple<int, int, int> tp = x;

    // Printing tupple elements
    cout << get<0>(tp) <<
            ' ' << get<1>(tp) <<
            ' ' << get<2>(tp) << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a multiset of tuples
  multiset<tuple<int, int,
  int> > multisetOfTuples;

  // Initializing tuples
  tuple<int, int,
  int> tuple1;
  tuple1 = make_tuple(4, 2, 3);

  tuple<int, int,
  int> tuple2;
  tuple2 = make_tuple(2, 3, 5);

  tuple<int, int,
  int> tuple3;
  tuple3 = make_tuple(2, 3, 5);

  tuple<int, int,
  int> tuple4;
  tuple4 = make_tuple(2, 1, 4);

  tuple<int, int,
  int> tuple5;
  tuple5 = make_tuple(4, 2, 3);

  // Inserting into multiset
  multisetOfTuples.insert(tuple1);
  multisetOfTuples.insert(tuple2);
  multisetOfTuples.insert(tuple3);
  multisetOfTuples.insert(tuple4);
  multisetOfTuples.insert(tuple5);

  // Calling print function
  print(multisetOfTuples);

  return 0;
}
```

**输出:**

> 2 1 4
> 2 3 5
> 2 3 5
> 4 2 3
> 4 2 3

**说明:**

在上面的输出中，多集合中总共有五个元组，其中(2，3，5)和(4，2，3)出现了两次。默认情况下，元组在多集中以非降序排列，并遵循以下逻辑:

1.  在多集合中，如果两个元组的第一个值相等，则比较元组的第二个值，如果它也相等，则比较第三个值。
2.  但是总是有可能将比较器传递给集合。

**示例 2:** 下面是 C++ 程序，演示将比较器传递给多集，该多集以非升序排列多组元组元素。

## C++

```cpp
// C++ program to demonstrate the
// implementation of multiset of 
// tuples by using custom comparator
#include <bits/stdc++.h>
using namespace std;

// Comparator for arranging elements
// in non-ascending order We can
// always modify the comparator as
// per the requirement
struct cmp
{
  // Arranging multiset elements in 
  // non-ascending order
  bool operator()(const tuple<int, int,
                              int>& x,
                  const tuple<int, int,
                              int>& y)
  {
    // If first elements of corrresponding 
    // tuples are equal
    if (get<0>(x) == get<0>(y))
    {
      // If second elements of corrresponding 
      // tuples are equal
      if (get<1>(x) == get<1>(y))
        return get<2>(x) > get<2>(y);

      return get<1>(x) > get<1>(y);
    }

    return get<0>(x) > get<0>(y);
  }
};

// Function to print multiset elements
void print(multiset<tuple<int, int,
           int>, cmp>& multisetOfTuples)
{
  for (auto x : multisetOfTuples)
  {
    // Each element of the multiset is 
    // tuple itself
    tuple<int, int, int> tp = x;

    // Printing tuple elements
    cout << get<0>(tp) <<
            ' ' << get<1>(tp) <<
            ' ' << get<2>(tp) << '\n';
  }
}

// Driver code
int main()
{
  // Declaring a multiset of tuples
  multiset<tuple<int, int,
                 int>, cmp> multisetOfTuples;

  // Initializing tuples
  tuple<int, int,
        int> tuple1;
  tuple1 = make_tuple(1, 2, 3);

  tuple<int, int,
        int> tuple2;
  tuple2 = make_tuple(2, 3, 5);

  tuple<int, int,
        int> tuple3;
  tuple3 = make_tuple(2, 3, 5);

  tuple<int, int,
        int> tuple4;
  tuple4 = make_tuple(2, 1, 4);

  tuple<int, int,
        int> tuple5;
  tuple5 = make_tuple(5, 8, 4);

  // Inserting into multiset
  multisetOfTuples.insert(tuple1);
  multisetOfTuples.insert(tuple2);
  multisetOfTuples.insert(tuple3);
  multisetOfTuples.insert(tuple4);
  multisetOfTuples.insert(tuple5);

  // Calling print function
  print(multisetOfTuples);

  return 0;
}
```

**输出:**

> 5 8 4
> 2 3 5
> 2 3 5
> 2 1 4
> 1 2 3

**说明:**

在上面的输出中，多集合中的元素按照非升序排列。值为(2，3，5)的元组在多集中有两个副本。