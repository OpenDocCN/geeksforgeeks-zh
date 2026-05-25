# 什么是追溯性数据结构？

> 原文：[https://www.geeksforgeeks.org/what-are-retroactive-data-structures/](https://www.geeksforgeeks.org/what-are-retroactive-data-structures/)

追溯数据结构是一种支持对[数据结构](https://www.geeksforgeeks.org/data-structures/)进行有效修改的数据结构类型，在这种新的数据结构范式中，对数据结构进行的操作不仅存在于现在，也存在于过去，这意味着即使在消遣时间间隔内，这些操作也可以改变和修改。

在处理需要定期更新的复杂应用程序时，这些数据结构在灵活性方面给了我们很大的安慰，因为调整结构可以根据程序的工作模型进行调整，在现实世界中，有各种情况需要从一系列操作中修改过去的操作。

## 追溯数据结构的需求

*   **实现动态化：** 一般来说，一些静态的[算法](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)需要一个动态的数据结构来处理它们的输入，追溯数据结构可以是使这些算法动态化的最佳解决方案。
*   **用于执行近似范围搜索：** 追溯数据结构有助于实现需要在任何时间点进行插入和删除等更新的操作，并在近似时间范围 `t` 内返回输入。
*   **避免额外的 `O(log n)` 开销：** 追溯数据结构帮助我们避免额外的 `O(log n)` 开销，并使应用程序能够执行操作，例如在段上构建高度的段树，用传统数据结构扩充根，用 `CDFC` 结构扩充节点。
*   **改变事务的历史顺序：** 追溯性数据结构使应用程序能够有效地适应各种条件，例如撤销以前发生的错误，而无需重新进行此后的所有工作。

## 与持久数据结构的比较

即使[持久数据结构](https://www.geeksforgeeks.org/persistent-data-structures/)和追溯数据结构的概念在考虑时间维度时看起来相似，但它们处理时间元素的方式仍然使它们彼此不同。

*   持久数据结构维护多个版本的数据结构，并且可以在一个版本的数据上实现操作来创建另一个版本。
*   在追溯数据结构的情况下，直接对以前的版本进行更改，并且不创建在过去经历数据更改的其他修改过的以前版本。

## 追溯的类型

### 1. 部分追溯

任何数据结构都可以通过一般转换进行部分追溯。例如，下面插入一个初始状态为 `[1, 2, 3, 4, 5]` 的部分追溯列表。然后，我们可以添加或删除当前的操作。

以下是上述概念的 Python 伪代码：

```python
# Python program to implement  
# the above approach  
x = PartiallyRetroactive([1, 2, 3, 4, 5])  
def appendOne(lst):
    return lst + [1]

# Three appendOnes by applying  
# insertAgo()
x.insertAgo(appendOne, tminus = 0)
x.insertAgo(appendOne, tminus = 0)
x.insertAgo(appendOne, tminus = 0)
x.query()

# Three appendOnes by applying insertAgo()
# [1, 2, 3, 4, 5, 1, 1, 1]   
```

**输出：**

```python
>>x.query() :
[1, 2, 3, 4, 5, 1, 1, 1]
```

我们还可以添加或删除过去的操作：

```python
def MethodForAppendNum(lst):
    return lst + [6]

# For Inserting into two operations ago
x.insertAgo(MethodForAppendNum, tminus=2)   
x.query()
# [1, 2, 3, 4, 5, 1, 6, 1, 1]

# For Deleting the first appendOne
x.deleteAgo(tminus=3)   
x.query()
# [1, 2, 3, 4, 5, 6, 1, 1]
```

**输出：**

```python
>>x.query() :
[1, 2, 3, 4, 5, 1, 6, 1, 1]
```

### 2. 一般完全追溯

完全追溯数据结构类似于它们的兄弟部分追溯数据结构，因为它们允许操作的追溯插入和删除。然而，完全追溯的数据结构也允许查询过去，而不仅仅是现在。

下面是上述方法的 Python 伪代码：

```python
b = FullyRetroactive([1,2,3])
b.insertAgo(appendOne, tminus = 0)

# This one should come last
b.insertAgo(MethodForAppendNum, tminus = 0)

# This one should come first
b.insertAgo(appendTen, tminus =2)

b.query()

# The current state of the data structure
# [1, 2, 3, 10, 1, 6]   
b.query(1)
# [1, 2, 3, 10, 1, 6]
b.query(2)
# [1, 2, 3, 10]
b.query(3)
# The state of the data structure way back in the past
# [1, 2, 3]   
```

**输出：**

```python
>>b.query(1) :
[1, 2, 3, 10, 1, 6]
>>b.query(2) :
[1, 2, 3, 10]
>>b.query(3) :
[1, 2, 3]
```

## 应用

追溯数据结构的一些应用如下：

*   **Recovery：** 如果我们的一个硬件芯片损坏，其上的数据丢失，但现在已修复，我们可以从传感器读取数据，并且我们希望将这些数据插入回系统，就像硬件从未损坏过一样。
*   **Error correction：** 数据输入不正确，因此需要纠正数据以消除错误输入的二次影响。
*   **Data manipulation in recreation area：** 在 recreation area 修改数据有助于在因系统错误或人为错误注入错误数据时进行损害控制。
*   **Bad data：** 在大规模系统中处理数据输入时，特别是在天气网络中的传感器等系统中，故障会导致大量自动数据传输，垃圾和错误数据可能对应用程序造成巨大损害。理想的解决方案是使用追溯数据结构删除过去操作中的坏数据，从而创建一个场景，例如，如果坏数据从未发生。

## 追溯性数据结构的优势

*   当数据崩溃时，无需使用成本高昂的回滚操作，这为我们提供了基于时间更新的灵活性。
*   这些数据结构可以最有效地应用于搜索问题，例如维护一组未知对象 `K`，这些对象受到插入、删除和查询 `(x, s)` 等操作的影响，因为在这里我们可以拥有按时间顺序返回和检索我们想要的查询来修改数据结构的特权。
*   这些数据结构帮助我们解决分解的搜索问题，例如形式为 `query(x, A∪B) = f(query(x, A), query(x, B))` 的查询在 `O(1)` 时间内运行。
*   它们有助于动态化静态算法。

## 追溯性数据结构的缺点

*   这些数据结构在更高的多项式时间内运行，并且需要更高的存储和计算资源。
*   这些数据结构适用于复杂的应用程序，这些应用程序仅依赖于基于时间的更新而没有适当的基于序列的目标，但不推荐用于简单且可扩展的应用程序，这些应用程序基于严格的规则生成及时更新，例如**员工考勤管理系统和一次性密码生成器**，因为此数据结构的实现将对更改和修改信息产生错误。
*   由于高多项式变换，涉及高维护成本。
*   如果通过追溯数据结构实现的应用程序没有涵盖有效的加密算法标准，则很可能存在有意的数据操作甚至无跟踪，因为没有可用的时间记录。

## 自动追溯

对于通过使用通用技术将数据结构自动转换为追溯形式的可能性，我们的头脑中自然会产生疑问，例如将指针机器模型转换为有效的部分追溯数据结构？这种通用技术将很好地补充现有的持久性数据结构，但是在追溯数据结构的情况下，追溯与持久性有着根本的不同，并且一般已知的技术并不适用。

解决这一普遍问题的一种简单方法是回滚方法，其中存储辅助信息，因为数据结构的所有更改都是由每个操作以这样一种方式进行的，即每个更改都可以动态反转。例如，为了启用内存写操作的回滚，我们存储先前在地址中的值，因此它们的性能根据追溯更改而有所不同。

## 追溯运行时间

取数据结构执行的若干操作，用于确定追溯数据结构的运行时间。例如，假设 `m` 是在结构上执行的操作数，`r` 是在追溯操作之前执行的操作数，`n` 是在任何时候结构中存在的最大元素数。