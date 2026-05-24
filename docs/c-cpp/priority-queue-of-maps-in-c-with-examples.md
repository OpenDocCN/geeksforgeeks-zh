# c++ 中地图的优先级队列，示例

> 原文:[https://www . geesforgeks . org/priority-queue-of-map-in-c-with-examples/](https://www.geeksforgeeks.org/priority-queue-of-maps-in-c-with-examples/)

**<u>优先队列</u>**

[**<u>【优先级队列】</u>**](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) 是容器适配器的一种类型，专门设计为队列的第一个元素是队列中所有元素中最大的，元素的顺序是非递增的(因此我们可以看到队列的每个元素都有优先级{固定顺序})。通常，优先级队列有两种类型:最大堆和最小堆，但是我们总是可以将比较器传递给优先级队列。

**与优先级队列一起使用的函数:**

*   **empty():** 此函数返回队列是否为空。
*   **size():** 这个函数返回队列的大小。
*   **top():** 返回对队列最顶端元素的引用。
*   **push(x):** 这个函数在队列的末尾添加元素‘x’。

**<u>地图</u>**

[](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)<u>是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。在内部，它被实现为自平衡 BST。</u>

<u>**与地图一起使用的功能:**</u>

*   <u>**begin():** 返回映射中第一个元素的迭代器</u>
*   <u>**end():** 返回映射中最后一个元素之后的理论元素的迭代器</u>
*   <u>**size():** 返回地图中元素的数量</u>
*   <u>**空():**返回地图是否为空</u>

<u>本文主要讨论如何在 C++ 中使用映射的优先级队列。在设计复杂的数据结构时，地图的优先级队列非常有用。</u>

<u>**<u>地图最大堆优先级队列:</u>**</u>

*   <u>映射以非降序排列的最大堆优先级队列:</u>

> <u>**priority_queue <地图< data_type1，data _ type 2>T5【priority queue；**</u>
> 
> <u>这里，
> **data_type1:** 是 key 的数据类型。
> **data_type2:** 是值的数据类型。</u>

*   <u>映射以非升序排列的最大堆优先级队列:</u>

> <u>**priority_queue <地图< data_type1，data_type2，大<data _ type 1>>>priority queue；**</u>
> 
> <u>这里，
> **data_type1:** 是 key 的数据类型。
> **data_type2:** 是值的数据类型。</u>

<u>**<u>地图的最小堆优先级队列:</u>**</u>

*   <u>映射以非降序排列的最小堆优先级队列:</u>

> <u>**priority _ queue<map<data _ type 1，data_type2 >，vector < map < data_type1，data_type2 > >，**
> **更大< map < data_type1，data _ type 2>>>priority queue；**</u>
> 
> <u>这里，
> **data_type1:** 为 key 的数据类型。
> **data_type2:** 为数值的数据类型。</u>

*   <u>映射以非升序排列的最小堆优先级队列:</u>

> <u>**priority _ queue<map<data _ type 1，data_type2 >，vector < map < data_type1，data_type2，更大的< data_type1 > > >，**
> T3】更大的< map < data_type1，data_type2，更大的<data _ type 1>>>T20】priority queue；</u>
> 
> <u>这里，
> **data_type1:** 为 key 的数据类型。
> **data_type2:** 为数值的数据类型。</u>

<u>**<u>地图定制优先级队列(使用比较器):</u>**</u>

> <u>priority_queue <map data_type2="">，vector <map data_type2="">>，
> my comparator>priority queue；</map></map></u>
> 
> <u>这里，
> **data_type1:** 为 key 的数据类型。
> **data_type2:** 为数值的数据类型。
> **myComparator:** 是比较器类或结构。</u>

<u>下面是比较器的 C++ 代码片段:</u>

## <u>C++ </u>

```cpp
// Comparator structure
struct myComparator
{
  int operator()(const map<data_type1, 
                           data_type2>& map1,
                 const map<data_type1, 
                           data_type2>& map2)
  {
    // body
  }
};

// Comparator class
struct myComparator 
{
  public:
  int operator()(const map<data_type1, 
                           data_type2>& map1,
                 const map<data_type1, 
                           data_type2>& map2)
  {
    // body
  }
};
```