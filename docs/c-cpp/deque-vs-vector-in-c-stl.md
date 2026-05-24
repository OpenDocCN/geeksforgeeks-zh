# c++ STL 中的 Deque vs Vector

> 原文:[https://www.geeksforgeeks.org/deque-vs-vector-in-c-stl/](https://www.geeksforgeeks.org/deque-vs-vector-in-c-stl/)

### [c++ 标准模板库(STL)中的 Deque](https://www.geeksforgeeks.org/deque-cpp-stl/)

双端队列是序列容器，具有两端伸缩的特点。
它们类似于[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)，但是在插入和删除元素的情况下更有效。与向量不同，可能无法保证连续的存储分配。
双端队列基本上是数据结构双端队列的一种实现。队列数据结构只允许在末尾插入，从前面删除。这就像现实生活中的排队，人从前面被移走，在后面被加上。双端队列是队列的一种特殊情况，可以在两端进行插入和删除操作。

德格的功能与[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)相同，只是增加了前后推送和弹出操作。

### [c++ STL 中的向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)

向量与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。向量元素被放在连续的存储中，这样就可以使用迭代器访问和遍历它们。在向量中，数据被插入到末尾。在末尾插入需要不同的时间，因为有时可能需要扩展数组。移除最后一个元素只需要恒定的时间，因为不会发生调整大小的情况。在开始或中间插入和擦除在时间上是线性的。

### 德格和矢量的区别:

<figure class="table">

| 矢量 | 双端队列 |
| Provide middle-end insertion and deletion mode. | Provide middle-end insertion and deletion method, beginning |
| Poor performance of front insertion and deletion. | Good performance of front insertion and deletion. |
| Continuous storage element | It contains a list of memory blocks of contiguous storage elements. |
| Adding and deleting elements has good performance. | Adding and deleting elements has poor performance. |

</figure>

**我们应该什么时候选择德格而不是 Vector？**
当我们的操作是在开头和结尾添加和删除元素(双端队列 ADT)时，我们必须选择 Deque。