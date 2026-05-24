# Python 中的 Binarytree 模块

> 原文：`https://www.geeksforgeeks.org/binarytree-module-in-python/`

二叉树是一种数据结构，其中每个节点或顶点都有至少两个子节点。在 Python 中，二叉树可以用不同的方式表示，节点有不同的数据结构（字典、列表）和类表示。然而，`binarytree` 库有助于直接实现二叉树。它还支持堆和二叉查找树（BST）。该模块没有预装 Python 的标准实用程序模块。要安装它，请在终端中键入以下命令。

```py
pip install binarytree 
```

## 创建节点

`Node` 类表示二叉树中特定节点的结构。这个类的属性是 `value`，`left`，`right`。

> **语法：** `binarytree.Node(value, left=None, right=None)`
> **参数：**
> **`value`：** 包含节点的数据。该值必须是数字。
> **`left`：** 包含左节点子节点的详细信息。
> **`right`：** 包含右侧节点子节点的详细信息。

**注意：** 如果 `left` 或 `right` 子节点不是 `Node` 的实例，然后引发 `binarytree.exceptions.NodeTypeError`，如果节点值不是数字，则引发 `binarytree.exceptions.NodeValueError`。

**示例：**

```py
from binarytree import Node
root = Node(3)
root.left = Node(6)
root.right = Node(8)

# Getting binary tree
print('Binary tree :', root)

# Getting list of nodes
print('List of nodes :', list(root))

# Getting inorder of nodes
print('Inorder of nodes :', root.inorder)

# Checking tree properties
print('Size of tree :', root.size)
print('Height of tree :', root.height)

# Get all properties at once
print('Properties of tree : \n', root.properties)
```

**输出：**

```
Binary tree : 3
/ \
6 8
List of nodes : [Node(3), Node(6), Node(8)]
Inorder of nodes : [Node(6), Node(3), Node(8)]
Size of tree : 3
Height of tree : 1
Properties of tree : 
 {'height': 1, 'size': 3, 'is_max_heap': False, 'is_min_heap': True, 'is_perfect': True, 'is_strict': True, 'is_complete': True}
```

## 从列表中构建二叉树

我们可以使用 `build()` 方法将值列表转换为二叉树，而不是重复使用 `Node` 方法。
这里，给定的列表包含树的节点，使得索引 `i` 处的元素在索引 `2*i+1` 处有它的左子元素，在索引 `2*i+2` 处有它的右子元素，在 `(i–1)//2` 处有它的父元素。索引 `j > len(list)//2` 的元素是叶节点。`None` 表示该索引处没有节点。使用 `values` 属性构建二叉树后，我们还可以得到节点列表。

> **语法：** `binarytree.build(values)`
> **参数：**
> **`values`：** 列出二叉树的表示。
> **返回：** 二叉树的根。

**示例：**

```py
# Creating binary tree
# from given list
from binarytree import build

# List of nodes
nodes = [3, 6, 8, 2, 11, None, 13]

# Building the binary tree
binary_tree = build(nodes)
print('Binary tree from list :\n',
      binary_tree)

# Getting list of nodes from
# binarytree
print('\nList from binary tree :',
      binary_tree.values)
```

**输出：**

```
Binary tree from list :

    ___3
   /    \
  6      8
 / \      \
2   11     13

List from binary tree : [3, 6, 8, 2, 11, None, 13]
```

## 构建随机二叉树

`tree()` 生成随机二叉树并返回其根节点。

> **语法：** `binarytree.tree(height=3, is_perfect=False)`
> **参数：**
> **`height`：** 它是树的高度，其值可以在 0-9（包括 0 和 9）
> **`is_perfect`：** 如果设置为 `True`，则会创建一个完美的二叉树。
> **返回：** 二叉树的根节点。

**示例：**

```py
from binarytree import tree

# Create a random binary
# tree of any height
root = tree()
print("Binary tree of any height :")
print(root)

# Create a random binary
# tree of given height
root2 = tree(height = 2)
print("Binary tree of given height :")
print(root2)

# Create a random perfect
# binary tree of given height
root3 = tree(height = 2,
             is_perfect = True)
print("Perfect binary tree of given height :")
print(root3)
```

**输出：**

```
Binary tree of any height :

      14____
     /      \
    2        5__
   /        /   \
  6        1     13
 /        /     /  \
7        9     4    8

Binary tree of given height :

  1__
 /   \
5     2
     / \
    4   3

Perfect binary tree of given height :

    __3__
   /     \
  2       4
 / \     / \
6   0   1   5
```

## 构建二叉查找树

二叉查找树是一种特殊类型的树数据结构，其顺序给出了节点或顶点的排序列表。在 Python 中，我们可以使用 `binarytree` 模块直接创建一个 BST 对象。`bst()` 生成一个随机二叉查找树并返回它的根节点。

> **语法：** `binarytree.bst(height=3, is_perfect=False)`
> **参数：**
> **`height`：** 它是树的高度，它的值可以在 0-9（包括 0 和 9）
> **`is_perfect`：** 如果设置为 `True`，则会创建一个完美的二叉树。
> **返回：** BST 的根节点。

**示例：**

```py
from binarytree import bst

# Create a random BST
# of any height
root = bst()
print('BST of any height : \n',
      root)

# Create a random BST of
# given height
root2 = bst(height = 2)
print('BST of given height : \n',
      root2)

# Create a random perfect
# BST of given height
root3 = bst(height = 2,
            is_perfect = True)
print('Perfect BST of given height : \n',
      root3)
```

**输出：**

```
BST of any height : 

        ____9______
       /           \
    __5__       ____12___
   /     \     /         \
  2       8   10         _14
 / \     /      \       /
1   4   7        11    13

BST of given height : 

   / \
  4   6
 /

Perfect BST of given height : 

    __3__
   /     \
  1       5
 / \     / \
0   2   4   6
```

## 导入堆

堆是一种树形数据结构，有两种类型：

*   最大堆
*   最小堆

使用 `binarytree` 库的 `heap()` 方法，我们可以生成一个随机的 max-heap 并返回它的根节点。要生成 min-heap，我们需要将 `is_max` 属性设置为 `False`。

> **语法：** `binarytree.heap(height=3, is_max=True, is_perfect=False)`
> **参数：**
> **`height`：** 它是树的高度，它的值可以在 0-9（包括 0 和 9）
> **`is_max`：** 如果设置为 `True`，则生成一个 max heap else min heap。
> **`is_perfect`：** 如果设置为 `True`，则会创建一个完美的二叉树。
> **返回：** 堆的根节点。

**示例：**

```py
from binarytree import heap

# Create a random max-heap
root = heap()
print('Max-heap of any height : \n',
      root)

# Create a random max-heap
# of given height
root2 = heap(height = 2)

print('Max-heap of given height : \n',
      root2)

# Create a random perfect
# min-heap of given height
root3 = heap(height = 2,
             is_max = False,
             is_perfect = True)

print('Perfect min-heap of given height : \n',
      root3)
```

**输出：**

```
Max-heap of any height : 

         _______14______
        /               \
    ___12__            __13__
   /       \          /      \
  10        8        3        9
 /  \      / \      / \      /
1    5    4   6    0   2    7

Max-heap of given height : 

    __6__
   /     \
  4       5
 / \     / \
2   0   1   3

Perfect min-heap of given height : 

    __0__
   /     \
  1       3
 / \     / \
2   6   4   5
```