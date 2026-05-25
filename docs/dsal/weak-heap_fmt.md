# 弱堆

> 原文: [https://www.geeksforgeeks.org/weak-heap/](https://www.geeksforgeeks.org/weak-heap/)

## 定义与性质

它是一棵二叉树，具有以下性质：
1.  节点右子树中的每一个键都大于节点本身存储的键。
2.  根没有左子节点。
3.  叶子只在树的最后两层找到。

它用于实现优先级队列。用户可能更喜欢弱堆而不是[二进制堆](https://www.geeksforgeeks.org/binary-heap/)的原因是，在最坏的情况下，弱堆能够执行较少的元素比较。

弱堆的基于数组的实现的插入和删除的最坏情况时间复杂度是：
1.  插入: `O(lg n)`
2.  删除: `O(lg n)`

弱堆构造使用支持常数时间插入的缓冲区。只要缓冲区大小低于阈值，就会将新元素插入缓冲区。一旦缓冲区满了，缓冲区的所有元素都会被移动到弱堆中。

## 基于数组的表示

弱堆是通过放宽二进制堆的要求获得的。为了表示内存中的弱堆，使用了两个数组。第一个是元素数组 `a`，另一个是反向位数组 `r`。

我们使用 `a_i` 来引用数组 `a` 的索引 `i` 处的元素或相应树结构中的节点。构建一个弱堆，使得对于 `a_i`，它的左子代的索引是 `2_i + r_i`，它的右子代的索引是 `2_i + 1 - r_i`，以及（`i != 0`）其父代的索引为 `\lfloor\dfrac{i}{2}\rfloor`。

**弱堆示例:**
如果给定 10 个整数作为输入，例如 8、7、4、5、2、6、9、3、11、1，那么由以下输入构造的弱堆将如下图所示。
![](img/a8c79f3adf7f500ccedc4ea3875fceb3.png)

## 操作与伪代码

基本的弱堆操作以及伪代码如下：

### 1. 尊贵的祖先

`a_j` 尊贵的祖先，`j != 0`，如果 `a_j` 是右子，则是 `a_j` 的父代，如果 `a_j` 是左子，则是 `a_j` 的父代的尊贵祖先。我们用 `d-ancestor(j)` 来表示这种祖先的索引。弱堆排序强制任何元素都不能小于其可分辨祖先的元素。

```
// Finding the distinguished ancestor in a weak heap
procedure: d-ancestor
input: j: index
while (j & 1) = r_\lfloor\dfrac{j}{2}\rfloor
    j \leftarrow \lfloor\dfrac{j}{2}\rfloor
return \lfloor\dfrac{j}{2}\rfloor
```

### 2. Join

子例程将两个弱堆组合成一个弱堆，条件是以下设置。连接需要 `O(1)` 个时间，因为它涉及一个元素比较。

```
// Joining two weak heaps
procedure: join
input: i, j: indices
if (!(a_j < a_i)){
    swap(a_i, a_j)
    r_j \leftarrow 1 - r_j
    return false
}
return true
```

### 3. 构造

通过执行 `n - 1` 对连接子例程的调用，可以使用 `n - 1` 元素比较来构造大小为 `n` 的弱堆。

```
//Constructing a weak heap
procedure: construct
input: a: array of n elements; r: array of n bits
for i \in {0, 1, . . ., n - 1}
    r_i \leftarrow 0
for j \in {n - 1, n - 2, . . ., 1}
    i \leftarrow d-ancestor(j)
    join(i, j)
```

### 4. 筛选

子例程 `sift-up(j)` 用于重新建立元素 `e`（最初在位置 `j`）和那些位于 `a_j` 祖先的元素之间的弱堆排序。从位置 `j` 开始，当 `e` 不在根处并且小于其可分辨祖先处的元素时，我们交换两个元素，翻转先前包含 `e` 的节点的位，并从 `e` 的新位置重复。

```
// reestablishing the weak-heap ordering
// on the path from a_j upwards
procedure: sift-up
input: j: index
while (j != 0){
    i \leftarrow d-ancestor(j)
    if join(i, j){
        break
    }
    j \leftarrow i
}
```

### 5. Insert

要插入元素 `e`，我们首先将 `e` 添加到下一个可用的数组条目中，使其成为堆中的一片叶子。如果这个叶子是它的父级的唯一的子级，我们通过更新父级的反向位使它成为左子级。为了重新建立弱堆排序，我们从 `e` 的位置开始调用筛选子例程。由此可见，插入需要 `O(lg n)` 时间，最多涉及 `\lceil lg n\rceil` 元素比较。

```
// Inserting an element into a weak heap.
procedure: insert
input: a: array of n elements; r: array of n bits; e: element
a_n \leftarrow e
r_n \leftarrow 0
if( (n & 1) = 0){
    r_\lfloor\dfrac{n}{2}\rfloor \leftarrow 0
}
sift-up(n)
++n
```

### 6. 向下筛选

子例程 `sift-down(j)` 用于在位置 `j` 的元素和 `a_j` 的右子树中的元素之间重新建立弱堆排序。从 `a_j` 的右子节点开始，识别 `a_j` 的右子树的左脊柱上的最后一个节点；这是通过重复访问左子节点直到到达没有左子节点的节点来完成的。从该节点到 `a_j` 的右子节点的路径向上遍历，并且在 `a_j` 和沿着该路径的节点之间重复执行连接操作。每次连接后，位置 `j` 处的元素小于或等于下一次连接中考虑的节点的左子树中的每个元素。

### 7. delete-min

要执行 `delete-min`，存储在弱堆根的元素将被存储在最后一个被占用的数组条目中的元素替换。为了恢复弱堆排序，需要对新根进行筛选。因此，`delete-min` 需要 `O(lg n)` 个时间，最多涉及 `lg n` 个元素的比较。

## 与其他堆结构的关系

弱堆的结构与二叉树排列相同。精确存储 `2^r` 元素的完美弱堆是秩为 `r` 的堆排序二叉树的二叉树表示。假设根在索引 0 处（在二进制堆中，左子节点为 `2k+1`，右子节点为 `2k+2`），则节点 `k` 的左子节点为 `2k`，右子节点为 `2k+2`。唯一不同的是弱堆的根没有左子，只有右子，存储在 `2*0+1=1` 的索引处。

弱堆的结构也非常类似于二项式堆，高度为 `h` 的树由一个根加上高度为 `h–1`，`h–2`，…，1 的树组成。像二项式堆一样，对弱堆的基本操作是合并两个高度相同的堆，形成一个高度为 `h+1` 的弱堆。这需要在根之间进行一次比较。哪个根更大（假设最大堆）就是最终根。最终根的第一个子级是丢失的根，它保留它的子级（右子树）。获胜根的子级作为失败根的同级插入。

弱堆的可区分属性是：
1.  它可以是不完美的（与二叉树相反）。
2.  是单棵树（与二项式队列形成对比，二项式队列是完美树的集合）。
3.  相当均衡。

## 应用

1.  它可以作为有效构建二进制堆的中间步骤。
2.  一个弱堆变量，允许一些元素违反弱堆排序，用于图搜索和网络优化，已知比斐波那契堆更好。