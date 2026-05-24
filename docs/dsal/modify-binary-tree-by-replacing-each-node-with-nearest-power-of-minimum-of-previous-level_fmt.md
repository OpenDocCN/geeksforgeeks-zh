# 通过用上一级最小的最近次幂替换每个节点来修改二叉树

> 原文: [https://www.geeksforgeeks.org/modify-binary-tree-by-replacing-each-node-with-nearest-power-of-minimum-of-previous-level/](https://www.geeksforgeeks.org/modify-binary-tree-by-replacing-each-node-with-nearest-power-of-minimum-of-previous-level/)

给定一个由 `N` 个节点组成的[二叉树](https://www.geeksforgeeks.org/binary-tree-data-structure/)，任务是在原始树中用每个节点的值与前一级最小值的最近幂替换每个节点的值后，打印[级次遍历](https://www.geeksforgeeks.org/level-order-tree-traversal/)。

> **注意:** 对于任意两个最近的幂的情况，选择其中的最大值。

**示例:**

> **输入:**
> ```
>       7
>      / \
>     4   11
>    /
>   23
> ```
> **输出:** `7 7 7 16`
> **说明:**
> *   级别 0 的节点值保持不变，即 `7`。
> *   最接近 `4` 的 `7` 的幂是 `7^1 = 7`。
>     最接近 `11` 的 `7` 次方是 `7^1 = 7`。
>     因此，1 级节点变为 `{7, 7}`。
> *   级别 1 的最小节点值为 `4`。
>     最接近 `23` 的 `4` 的幂是 `4^4 = 16`。
>     因此，2 级节点变为 `{16}`。
>
> 完成上述操作后的结果树如下:
> ```
>       7
>      / \
>     7   7
>    /
>   16
> ```

> **输入:**
> ```
>        3
>      /   \
>     2     6
>    / \   / \
>   45 71 25  T9
> ```
> **输出:** `3 9 32 64 N 32`

## 方法

思路是使用[队列](https://www.geeksforgeeks.org/queue-data-structure/)执行[级顺序遍历](https://www.geeksforgeeks.org/level-order-tree-traversal/)来解决问题。

按照以下步骤解决问题:

1.  定义一个函数，比如 `nearestPow(X, Y)`，求一个整数 `X` 的最近的 `Y` 的幂:
    *   找到 `log(X) base Y` 并将其存储在一个变量中，比如 `K`。
    *   如果 `ABS(X - Y^K)` 小于 `ABS(Y^(K+1) - X)`，则返回 `Y^K`。否则，返回 `Y^(K + 1)`。
2.  初始化两个变量，比如 `minCurr` 和 `minPrev`，分别存储当前级别的最小值和前一级别的最小值。
3.  首先分配 `minPrev = root.val` 并初始化一个队列，比如 `Q`，来存储节点进行等级顺序遍历。
4.  当 `Q` [不空时](https://www.geeksforgeeks.org/queueempty-queuesize-c-stl/)迭代:
    *   将队列的第一个节点存储在一个变量中，比如 `temp`，从队列 `Q` 中删除第一个节点。
    *   将 `minPrev` 的值分配给 `minCurr` 并更新 `minCurr = 10^18`。
    *   迭代范围 `[0, length(Q) - 1]` 并将 `minCurr` 更新为 `minCurr = min(minCurr, temp.val)`，并将整数 `minPrev` 的最近幂指定给 `temp.val`。
    *   在上述步骤的每次迭代中，如果各个节点不是 `null`，则向左推 `temp` 和向右推 `temp`。
5.  完成以上步骤后，[打印更新树的层级顺序遍历](https://www.geeksforgeeks.org/level-order-traversal-line-line-set-3-using-one-queue/)。

下面是上述方法的实现:

### Python 3

```python
# Python program for the above approach
import math

# Structure of a Node of a Tree
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

# Function to calculate the
# nearest power of an integer
def nearestPow(x, base):
    k = int(math.log(x, base))
    if abs(base**k - x) < abs(base**(k+1) - x):
        return base**k
    else:
        return base**(k+1)

# Iterative method to perform
# Level Order Traversal
def printLevelOrder(root):

    # Base Case
    if root is None:
        return

    # Queue for Level Order Traversal
    q = []

    # Enqueue root
    q.append(root)

    while q:

        # Stores number of nodes at current level
        count = len(q)

        # Dequeue all nodes of the current
        # level and Enqueue all nodes of
        # the next level
        while count > 0:
            temp = q.pop(0)
            print(temp.val, end=' ')

            # Push the left subtree if not empty
            if temp.left:
                q.append(temp.left)

            # Push the right subtree if not empty
            if temp.right:
                q.append(temp.right)

            # Decrement count by 1
            count -= 1

# Function to replace each node
# with nearest power of minimum
# value of previous level
def replaceNodes(root):

    # Stores the nodes of tree to
    # traverse in level order
    que = [root]

    # Stores current level
    lvl = 1

    # Stores the minimum
    # value of previous level
    minPrev = root.val

    # Stores the minimum
    # value of current level
    minCurr = root.val

    # Iterate while True
    while True:

        # Stores length of queue
        length = len(que)

        # If length is zero
        if not length:
            break

        # Assign minPrev = minCurr
        minPrev = minCurr
        minCurr = 1000000000000000000

        # Iterate over range [0, length - 1]
        while length:

            # Stores current node of tree
            temp = que.pop(0)

            # Update minCurr
            minCurr = min(temp.val, minCurr)

            # Replace current node with
            # nearest power of minPrev
            temp.val = nearestPow(temp.val, minPrev)

            # Left child is not Null
            if temp.left:

                # Append temp.left node in the queue
                que.append(temp.left)

            # If right child is not Null
            if temp.right:

                # Append temp.right node in the queue
                que.append(temp.right)

            # Decrement length by one
            length -= 1

        # Increment level by one
        lvl += 1

    # Function Call to perform the
    # Level Order Traversal
    printLevelOrder(root)

# Driver Code

# Given Tree
root = TreeNode(7)
root.left = TreeNode(4)
root.right = TreeNode(11)
root.left.right = TreeNode(23)

replaceNodes(root)
```

**Output:**

```
7 7 7 16
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`