# c++ STL 中多集和多映射对的区别

> 原文:[https://www . geesforgeks . org/multist-t 和 multimap-in-c-stl/](https://www.geeksforgeeks.org/difference-between-pair-in-multiset-and-multimap-in-c-stl/) 中的配对差异

[**c++**](https://www.geeksforgeeks.org/pair-in-cpp-stl/)**中的 Pairs:**pair 容器是在<实用工具>头中定义的简单容器，由两个数据元素或对象组成。第一个元素被称为“第一”，第二个元素被称为“第二”，顺序是固定的(第一，第二)。Pair 用于将两个类型可能不同的值组合在一起。Pair 提供了一种将两个异构对象存储为一个单元的方法。

**语法:**

> **pair (data_type1，data _ type 2)Pair _ name**；

[**【c++ 中的多集】**](https://www.geeksforgeeks.org/multiset-in-cpp-stl/) **:** 多集是一种关联容器，按照特定的顺序存储元素，多个元素可以具有相同的值。

**语法:**

> **多集<数据类型>多集 _ 名称；**

[](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/)****:**多图是一种关联容器，类似于 [**图**](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) ，不同的是多个元素可以有相同的键。**

****语法:****

> ****多地图<数据 _ 类型 1，数据 _ 类型 2 >多地图 _ 名称****

****多集成对和** [**C++ STL**](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) **多图有什么区别？****

**这两种数据结构 multiset 和 multimap 的默认行为是以升序存储元素。当创建一对多集的**时，默认情况下，它将根据所有对的**第一元素**按照**递增顺序对所有的**对**进行排序，如果任意两对或两对以上对的第一元素**相等**，则它将根据对**的**第二元素对该对进行排序。******

默认情况下，当创建一对多映射时，它将根据所有对的**第一个元素**对所有对进行排序，如果任意两个或两个以上对的第一个元素相等，则它将根据插入到多映射对的**顺序打印该对。**

以下是说明差异的程序:

**程序 1:** 多组配对

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program print the data of
// multiset by inserting using pair
#include <bits/stdc++.h>
using namespace std;

// Function to print the data stored
// in pair of multiset
void printData(multiset<pair<int, string> > gfg)
{

    // Declare iterator
    multiset<pair<int, string> >::iterator i;

    // Iterate through pair of multiset
    for (i = gfg.begin(); i != gfg.end(); ++ i) {

        // Print the pairs
        cout << i->first << " "
<< i->second << endl;
    }
}

// Driver Code
int main()
{
    // Declare pair of multiset
    multiset<pair<int, string> > gfg;

    // Insert Data
    gfg.insert(make_pair(1, "yukti"));
    gfg.insert(make_pair(2, "umang"));
    gfg.insert(make_pair(3, "vinay"));
    gfg.insert(make_pair(3, "vijay"));
    gfg.insert(make_pair(4, "kanak"));

    // Function call to print the data
    printData(gfg);
    return 0;
}
```

**说明:**
在上面的程序中我们创建了**对**的整数和字符串，其中名称与每个整数配对，并插入到**多组**中。根据多组默认行为，数据按照**第一个元素**按照**上升**的顺序排列，但是当第一个元素**相同时**会按照**第二个值**排列这些元素。对于对(3，“vijay”)和(3，“vinay”)而言，对**中的第一个元素，即** 3 对于**“vijay”**和**“vinay”**都是相同的，因此它将根据第二个元素**“vijay”**然后**“vinay”**来排列对(按字母顺序)。

**程序 2:** 多地图配对

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program print the data of
// multimap by inserting using pair
#include <bits/stdc++.h>
using namespace std;

// Function to print the data stored
// in pair of multimap
void printData(multimap<int, string> gfg)
{

    // Declare iterator
    multimap<int, string>::iterator i;

    // Iterate through pair of multiset
    for (i = gfg.begin(); i != gfg.end(); ++ i) {

        // Print the pairs
        cout << i->first << " "
<< i->second << endl;
    }
}

// Driver Code
int main()
{
    // Declare pair of multimap
    multimap<int, string> gfg;

    // Insert data
    gfg.insert(make_pair(1, "yukti"));
    gfg.insert(make_pair(2, "umang"));
    gfg.insert(make_pair(3, "vinay"));
    gfg.insert(make_pair(3, "vijay"));
    gfg.insert(make_pair(4, "kanak"));

    // Function call to print the data
    printData(gfg);

    return 0;
}
```

**Output**

```cpp
1 yukti
2 umang
3 vinay
3 vijay
4 kanak
```

**以上代码解释:**
在上面的程序中，我们再次**插入了**相同的**对**但是这次是在**多图**中。根据**多映射**的默认行为，数据按照键按照**升序排列**，但是当键相同时，与**多设置**不同，它会看到**优先**哪个元素先插入**然后按照这个顺序排列。因此，如所示的输出中，我们可以看到，由于键 **3** 对于**“维奈”**和**“维贾伊”**是相同的，因此它将遵循**对**插入到**多图**中的顺序，这就是为什么在输出中，**“维奈”**排在**“维贾伊”**之前。** 

****表格区分:**** 

<figure class="table"> **| Pairing in multiple set pairs | Multi-mapping |
| --- | --- |
| Pairs in multiple set pairs are used to map keys with specific values. | The default behavior is to insert elements as key-value pairs. |
| When a one-to-many set is created, by default, it will sort all pairs in ascending order according to the first element of all pairs, and if the first elements of any two or more pairs are equal, it will sort the pair according to the second element of the pair. | When a pair of multiple mappings is created, by default, it will sort all pairs in ascending order according to the first element of all pairs. If the first elements of any two or more pairs are equal, it will print the pair according to the order in which the multiple mappings are inserted. |
| 语法:

> 多集<对< int，串>>M；

 | 句法:

> multimap<int，string>M；

 |** </figure>