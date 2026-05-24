# c++ 中的序列与关联容器

> 原文:[https://www . geesforgeks . org/sequence-vs-associative-containers-CPP/](https://www.geeksforgeeks.org/sequence-vs-associative-containers-cpp/)

**序列容器**

在标准模板库中，它们引用了一组**容器类模板**，我们用它们来存储数据。顾名思义，一个共同的属性是元素**可以顺序访问。**
以下每个容器使用不同的算法进行数据存储，因此对于不同的操作，它们具有不同的速度。容器中的所有元素应为**相同类型**。

1.  数组=它实现**不可调整大小的数组。**
    ex:int arr[10]；//固定大小 10 的数组。
2.  [向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/) =它实现了动态数组与**更快的随机访问，**这些非常有用，因为不像数组，它们可以调整大小。
    例:矢量<int>v；int 类型的向量
3.  [出列](https://www.geeksforgeeks.org/deque-cpp-stl/)用**更快的随机访问**
    实现**双端排队**例如:出队 dq；//字符类型出列
4.  [forward_list](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) :实现单链表。
    例:forward _ list flint 类型的 forward_list。
5.  [列表](https://www.geeksforgeeks.org/list-cpp-stl/):实现**双链表**。
    例:名单 l；int 列表

**关联容器**

在标准模板库中，它们指的是用于实现**关联数组的一组类模板。**它们用于存储元素，但对其元素有一些限制。
这些集装箱的两个重要特点是

1.  有一把钥匙。在地图和集合的情况下，键是唯一的。在多映射和多集合的情况下，允许一个键有多个值。对于 map 和 multimap，存在键值对。在 set 的情况下，只有键。
2.  元素遵循 [***严格弱排序***T5***。*** 。](https://en.wikipedia.org/wiki/Weak_ordering#Strict_weak_orderings)

以下是关联容器下的内容

1.  [地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/):这里我们创建的每个键都必须是唯一的。
    ex:地图极客 _ no//这里第一个数据类型是键，第二个数据类型是值
2.  [设置](https://www.geeksforgeeks.org/set-in-cpp-stl/):这里我们创建的键也必须是唯一的，但是与地图的一个重要区别是在这里 ***值本身作为一个键*** 所以它意味着设置中的元素是唯一的，即没有重复。
    ex:套装 s；//值本身充当一个键。
3.  [多地图](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/):和地图一样，但是这里的钥匙需要*而不是*是唯一的。
    ex: multimap 极客 _ no
4.  [多集](https://www.geeksforgeeks.org/multiset-in-cpp-stl/):和集合一样，但是这里元素的唯一性*不重要*也就是说，我们可以不像集合一样多次拥有同一个元素。
    例如:多集标记；

**序列容器中的序列 vs 关联(复杂性方面)**

1.  简单的插入需要恒定的时间。
2.  前线有不变的摊销时间。
3.  中间插入相当慢。

在关联容器中，大多数复杂性都是以对数来表示的

1.  插入一个元素是 0(对数 n)
2.  移除元素 0(对数 n)
3.  搜索元素 0(对数 n)
4.  递增或递减迭代器 O(1)(摊销)
5.  中间插入更快。

**无序关联容器**

请注意，每个关联容器都有无序的关联容器，其中包含没有任何特定顺序的元素。无序关联容器的例子有[无序 _ 集合](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)、[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)、[无序 _ 多映射](https://www.geeksforgeeks.org/unordered_multimap-and-its-application/)、[无序 _ 多集合](https://www.geeksforgeeks.org/unordered_multiset-and-its-uses/)。