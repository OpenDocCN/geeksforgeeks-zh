# Javascript 中二叉查找树的实现

> 原文：`https://www.geeksforgeeks.org/implementation-binary-search-tree-javascript/`

在本文中，我们将用 Javascript 实现[二叉查找树](https://www.geeksforgeeks.org/binary-search-tree-set-1-search-and-insertion/)数据结构。树是由一些边连接的节点的集合。一个[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)是一个非线性的数据结构。二叉查找树是一个二叉树，其中具有较小值的节点存储在左边，而具有较大值的节点存储在右边。

现在我们来看一个二叉查找树节点的例子：

```
// Node class
class Node
{
    constructor(data)
    {
        this.data = data;
        this.left = null;
        this.right = null;
    }
}
```

在上面的代码片段中，我们定义了一个节点类，它有三个属性`data`、`left`和`right`，`left`和`right`是二叉查找树中左和右节点的指针。`data`用`data`初始化，该数据在创建该节点的对象并将左右设置为空时传递。

现在让我们看一个二叉查找树类的例子。

```
// Binary Search tree class
class BinarySearchTree
{
    constructor()
    {
        // root of a binary search tree
        this.root = null;
    }

    // function to be implemented
    // insert(data)
    // remove(data)

    // Helper function
    // findMinNode()
    // getRootNode()
    // inorder(node)
    // preorder(node)               
    // postorder(node)
    // search(node, data)
}
```

上面的例子展示了一个二叉查找树类的框架，它包含一个私有变量`root`，这个变量保存了一棵树的根，它被初始化为`null`。

现在让我们实现每个功能：

**1. `insert(data)`** – 它在树中插入一个新节点，值为`data`。

```
// helper method which creates a new node to
// be inserted and calls insertNode
insert(data)
{
    // Creating a node and initialising
    // with data
    var newNode = new Node(data);

    // root is null then node will
    // be added to the tree and made root.
    if(this.root === null)
        this.root = newNode;
    else

        // find the correct position in the
        // tree and add the node
        this.insertNode(this.root, newNode);
}

// Method to insert a node in a tree
// it moves over the tree to find the location
// to insert a node with a given data
insertNode(node, newNode)
{
    // if the data is less than the node
    // data move left of the tree
    if(newNode.data < node.data)
    {
        // if left is null insert node here
        if(node.left === null)
            node.left = newNode;
        else

            // if left is not null recur until
            // null is found
            this.insertNode(node.left, newNode);
    }

    // if the data is more than the node
    // data move right of the tree
    else
    {
        // if right is null insert node here
        if(node.right === null)
            node.right = newNode;
        else

            // if right is not null recur until
            // null is found
            this.insertNode(node.right,newNode);
    }
}
```

在上面的代码中我们有两种方法`insert(data)`和`insertNode(node, newNode)`。让我们一个一个来理解：

*   **`insert(data)`** – 它创建一个值为`data`的新节点。如果树是空的，它将这个节点添加到树中使其成为根。否则，它调用`insertNode(node, data)`。
*   **`insertNode(node, data)`** – 它将给定的`data`与当前节点的数据进行比较，并相应地移动到左边或右边，重复此过程直到可以添加正确的`null`节点。

**2. `remove(data)`** – 该函数移除具有给定数据的节点。

```
// helper method that calls the
// removeNode with a given data
remove(data)
{
    // root is re-initialized with
    // root of a modified tree.
    this.root = this.removeNode(this.root, data);
}

// Method to remove node with a
// given data
// it recur over the tree to find the
// data and removes it
removeNode(node, key)
{

    // if the root is null then tree is
    // empty
    if(node === null)
        return null;

    // if data to be delete is less than
    // roots data then move to left subtree
    else if(key < node.data)
    {
        node.left = this.removeNode(node.left, key);
        return node;
    }

    // if data to be delete is greater than
    // roots data then move to right subtree
    else if(key > node.data)
    {
        node.right = this.removeNode(node.right, key);
        return node;
    }

    // if data is similar to the root's data
    // then delete this node
    else
    {
         // deleting node with no children
        if(node.left === null && node.right === null)
        {
            node = null;
            return node;
        }

        // deleting node with one children
        if(node.left === null)
        {
            node = node.right;
            return node;
        }

        else if(node.right === null)
        {
            node = node.left;
            return node;
        }

        // Deleting node with two children
        // minimum node of the right subtree
        // is stored in aux
        var aux = this.findMinNode(node.right);
        node.data = aux.data;

        node.right = this.removeNode(node.right, aux.data);
        return node;
    }

}
```