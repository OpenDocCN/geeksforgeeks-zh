# 用链表中的剩余计数替换每个节点

> 原文:[https://www . geesforgeks . org/将每个节点替换为其-super Asser-count-in-link-list/](https://www.geeksforgeeks.org/replace-each-node-with-its-surpasser-count-in-linked-list/)

给定 LinkedList，将每个节点的值替换为其 surpasser 计数。这是右边的元素数。
**例:**

> **输入:**10->12->5->40->21->70->1->49->37->NULL
> T3】输出:6->5->5->2->3->0->2->0-【T50 因此将节点更换为 **6** 。第一个节点中的
> 元素为 **12** ，节点右侧大于 **12** 的元素个数为 **5** 。因此将节点更换为 **5** 。
> 同样，替换列表中的所有元素。
> **输入:**5->4->6->3->2->NULL
> **输出:**1->1->0->0->0->NULL

**简单方法**

1.  取两个指针 **p** 和 **x** 。指针 **p** 用于遍历列表， **x** 用于遍历列表右半部分的每个节点。
2.  初始化一个变量*计数*来计数大于当前节点的节点。
3.  使用指针 p 遍历列表中的所有节点。
    *   将计数初始化为 0。
    *   初始化指针 **x** 指向当前节点 **p** 。
    *   计算大于当前节点的节点数。
    *   用计数替换当前节点。
4.  重复步骤 4，直到完全遍历完列表。

以下是上述方法的实现:

## C++

```cpp
// C++ program to replace the nodes
// with their surpasser count

#include <bits/stdc++.h>
using namespace std;

// A linked list node
struct Node {
    int data;
    struct Node* next;
};

// Utility function to create a new Node
Node* newNode(int data)
{
    Node* temp = new Node;
    temp->data = data;
    temp->next = NULL;

    return temp;
}

// Function to display the linked list
void printList(Node* node)
{
    while (node != NULL) {

        cout << node->data << " ";

        node = node->next;
    }
}

// Function to check Surpasser Count
void replaceNodes(Node* head)
{
    // Pointer used to traverse through
    // all the nodes in the list
    Node* p = head;

    // Pointer used to traverse through the right
    // elements to count the greater elements
    Node* x = NULL;

    // Variable to count the number of
    // elements greater than the
    // current element on right
    int count = 0;

    int i;

    // Traverse through all the elements
    // in the list
    while (p != NULL) {

        count = 0;

        i = 0;

        // Initialize x to current node
        x = p;

        // Check or count the number of nodes
        // that are greater than the current
        // node on right
        while (x != NULL) {

            if (x->data > p->data)
                count++ ;

            x = x->next;
        }

        // Replace the node data with the
        // count of elements greater than
        // the current element
        p->data = count;
        p = p->next;
    }
}

// Driver code
int main()
{
    // Creating the linked list
    Node* head = newNode(10);
    head->next = newNode(12);
    head->next->next = newNode(5);
    head->next->next->next = newNode(40);
    head->next->next->next->next = newNode(21);
    head->next->next->next->next->next = newNode(70);
    head->next->next->next->next->next->next = newNode(1);
    head->next->next->next->next->next->next->next = newNode(49);
    head->next->next->next->next->next->next->next->next = newNode(37);

    replaceNodes(head);

    printList(head);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to replace the nodes
// with their surpasser count

class GFG {

// A linked list node
static class Node {
    int data;
    Node next;
};

// Utility function to create a new Node
static Node newNode(int data)
{
    Node temp = new Node();
    temp.data = data;
    temp.next = null;

    return temp;
}

// Function to display the linked list
static void printList(Node node)
{
    while (node != null) {
        System.out.print(node.data+" ");

        node = node.next;
    }
}

// Function to check Surpasser Count
static void replaceNodes(Node head)
{
    // Pointer used to traverse through
    // all the nodes in the list
    Node p = head;

    // Pointer used to traverse through the right
    // elements to count the greater elements
    Node x = null;

    // Variable to count the number of
    // elements greater than the
    // current element on right
    int count = 0;

    int i;

    // Traverse through all the elements
    // in the list
    while (p != null) {

        count = 0;

        i = 0;

        // Initialize x to current node
        x = p;

        // Check or count the number of nodes
        // that are greater than the current
        // node on right
        while (x != null) {

            if (x.data > p.data)
                count++ ;

            x = x.next;
        }

        // Replace the node data with the
        // count of elements greater than
        // the current element
        p.data = count;
        p = p.next;
    }
}

// Driver code
public static void main(String[] args) {
  // Creating the linked list
    Node head = newNode(10);
    head.next = newNode(12);
    head.next.next = newNode(5);
    head.next.next.next = newNode(40);
    head.next.next.next.next = newNode(21);
    head.next.next.next.next.next = newNode(70);
    head.next.next.next.next.next.next = newNode(1);
    head.next.next.next.next.next.next.next = newNode(49);
    head.next.next.next.next.next.next.next.next = newNode(37);

    replaceNodes(head);

    printList(head);
    }
}

// This code has been contributed by 29AjayKumar
```

## 蟒蛇 3

```cpp
# Python3 program to replace the nodes
# with their surpasser count

# A linked list node
class Node:

    def __init__(self, data):
        self.data = data
        self.next = None

# Function to display the linked list
def printList(node):

    while node != None:
        print(node.data, end = " ")
        node = node.next

# Function to check Surpasser Count
def replaceNodes(head):

    # Pointer used to traverse through
    # all the nodes in the list
    p = head

    # Pointer used to traverse through
    # the right elements to count the
    # greater elements
    x = None

    # Variable to count the number of
    # elements greater than the
    # current element on right
    count = 0

    # Traverse through all the elements
    # in the list
    while p != None:

        count = 0

        # Initialize x to current node
        x = p

        # Check or count the number of nodes
        # that are greater than the current
        # node on right
        while x != None:

            if x.data > p.data:
                count += 1

            x = x.next

        # Replace the node data with the
        # count of elements greater than
        # the current element
        p.data = count
        p = p.next

# Driver code
if __name__ == "__main__":

    # Creating the linked list
    head = Node(10)
    head.next = Node(12)
    head.next.next = Node(5)
    head.next.next.next = Node(40)
    head.next.next.next.next = Node(21)
    head.next.next.next.next.next = Node(70)
    head.next.next.next.next.next.next = Node(1)
    head.next.next.next.next.next.next.next = Node(49)
    head.next.next.next.next.next.next.next.next = Node(37)

    replaceNodes(head)

    printList(head)

# This code is contributed by Rituraj Jain
```

## C#

```cpp
// C# program to replace the nodes
// with their surpasser count
using System;

class GFG
{

// A linked list node
public class Node
{
    public int data;
    public Node next;
};

// Utility function to create a new Node
static Node newNode(int data)
{
    Node temp = new Node();
    temp.data = data;
    temp.next = null;

    return temp;
}

// Function to display the linked list
static void printList(Node node)
{
    while (node != null)
    {
        Console.Write(node.data + " ");

        node = node.next;
    }
}

// Function to check Surpasser Count
static void replaceNodes(Node head)
{
    // Pointer used to traverse through
    // all the nodes in the list
    Node p = head;

    // Pointer used to traverse through the right
    // elements to count the greater elements
    Node x = null;

    // Variable to count the number of
    // elements greater than the
    // current element on right
    int count = 0;

    int i;

    // Traverse through all the elements
    // in the list
    while (p != null)
    {

        count = 0;

        i = 0;

        // Initialize x to current node
        x = p;

        // Check or count the number of nodes
        // that are greater than the current
        // node on right
        while (x != null)
        {

            if (x.data > p.data)
                count++ ;

            x = x.next;
        }

        // Replace the node data with the
        // count of elements greater than
        // the current element
        p.data = count;
        p = p.next;
    }
}

// Driver code
public static void Main()
{
    // Creating the linked list
    Node head = newNode(10);
    head.next = newNode(12);
    head.next.next = newNode(5);
    head.next.next.next = newNode(40);
    head.next.next.next.next = newNode(21);
    head.next.next.next.next.next = newNode(70);
    head.next.next.next.next.next.next = newNode(1);
    head.next.next.next.next.next.next.next = newNode(49);
    head.next.next.next.next.next.next.next.next = newNode(37);

    replaceNodes(head);

    printList(head);
}
}

/* This code contributed by PrinciRaj1992 */
```

## java 描述语言

```cpp
<script>

// JavaScript program to replace the nodes
// with their surpasser count

// A linked list node
class Node {
        constructor() {
                this.data = 0;
                this.next = null;
             }
        }

// Utility function to create a new Node
function newNode( data)
{
    var temp = new Node();
    temp.data = data;
    temp.next = null;

    return temp;
}

// Function to display the linked list
function printList( node)
{
    while (node != null) {
        document.write(node.data+" ");

        node = node.next;
    }
}

// Function to check Surpasser Count
function replaceNodes( head)
{
    // Pointer used to traverse through
    // all the nodes in the list
    var p = head;

    // Pointer used to traverse through the right
    // elements to count the greater elements
    var x = null;

    // Variable to count the number of
    // elements greater than the
    // current element on right
    let count = 0;

    let i;

    // Traverse through all the elements
    // in the list
    while (p != null) {

        count = 0;

        i = 0;

        // Initialize x to current node
        x = p;

        // Check or count the number of nodes
        // that are greater than the current
        // node on right
        while (x != null) {

            if (x.data > p.data)
                count++ ;

            x = x.next;
        }

        // Replace the node data with the
        // count of elements greater than
        // the current element
        p.data = count;
        p = p.next;
    }
}

// Driver Code

// Creating the linked list
var head = newNode(10);
head.next = newNode(12);
head.next.next = newNode(5);
head.next.next.next = newNode(40);
head.next.next.next.next = newNode(21);
head.next.next.next.next.next = newNode(70);
head.next.next.next.next.next.next = newNode(1);
head.next.next.next.next.next.next.next = newNode(49);
head.next.next.next.next.next.next.next.next = newNode(37);

replaceNodes(head);

printList(head);

</script>
```

**Output**

```cpp
6 5 5 2 3 0 2 0 0 
```

**时间复杂度** : O(N <sup>2</sup> )，其中 N 为链表中的节点数。
**辅助空间** : O(1)

**PBDS 和哈希映射的另一种方法**

我们可以列出我们的要求和方法来观察并找到解决方案。我们的方法:

1.向后遍历链表(所以我们不关心当前左边的元素)

2.将当前元素存储在排序的数据结构中(任何时间点，元素都在我们的数据结构中排序)

3.在我们的排序数据结构中找到大于当前元素的元素总数，并用它替换当前元素

为了向后遍历链表，我们将使用递归。

我们可以用 PBDS。有了 PBDS，我们可以找到比特定的键更小的元素。有了严格的小，我们可以添加当前元素并从所有元素中减去它。所以基本上:

> 大于当前的元素= PBDS 元素总数–(在 PBDS 查询以查找严格小于当前元素的元素)–(当前元素+等于当前元素)

PBDS 不允许重复元素。但是对于计数部分，我们需要重复的元素。因此，我们将在 PBDS 插入一对(第一个=元素，第二个=索引)，使每个条目唯一。之后，为了找到与当前元素相等的元素总数，我们将使用一个哈希映射。在哈希映射中，我们将存储元素的总出现次数(基本的整数到整数映射)。

**注**:我们也可以构建自己的数据结构，满足我们所陈述的当前需求。按排序顺序插入重复项，并查询大于关键字的元素。但是在这篇文章中，我们将使用 C++ STL DS 来做这件事。

## C++

```cpp
#include <iostream>
#include <unordered_map>

// library for PBS
#include <ext/pb_ds/assoc_container.hpp>
#include <ext/pb_ds/tree_policy.hpp>

// PBDS of pair<int, int>
#define oset tree<pair<int, int>, null_type,less<pair<int, int>>, rb_tree_tag,tree_order_statistics_node_update>

using namespace std;
using namespace __gnu_pbds;

// Linked list storage
class Node {
    public:
    int value;
    Node* next;
    Node(int value) {
        this->value = value;
        next = NULL;
    }
};

/*

head => head is the head of the linked list
os => unordered_set or PBDS
mp => Hash map to store count of each element
count => count of element from backwards

*/

void solve(Node* head, oset& os, unordered_map<int, int>& mp, int& count) {
    if(head == NULL) return;
    solve(head->next, os, mp, count);
    // we first call our recursion and then compute to traverse the linked list backwards on recursion return
    // increament count backwards
    count++ ;
    // inserting elements into PBDS with indexes starting from backwards
    os.insert({head->value, count});
    // mapping elements to count
    mp[head->value]++ ;
    // formula: total elements in PBDS - total number of elements equal to current - elements smaller than current
    int numberOfElements = count - mp[head->value] - os.order_of_key({head->value, -1});
    // replace the linked list current element to the number of elements greater than the current
    head->value = numberOfElements;
}

void printList(Node* head) {
    while(head) {
        cout << head->value << (head->next ? "->" : "");
        head = head->next;
    }
    cout << "\n";
}

int main() {
    Node* head = new Node(43);
    head->next = new Node(65);
    head->next->next = new Node(12);
    head->next->next->next = new Node(46);
    head->next->next->next->next = new Node(68);
    head->next->next->next->next->next = new Node(85);
    head->next->next->next->next->next->next = new Node(59);
    head->next->next->next->next->next->next->next = new Node(85);
    head->next->next->next->next->next->next->next->next = new Node(37);
    oset os;
    unordered_map<int, int> mp;
    int count = 0;
    printList(head);
    solve(head, os, mp, count);
    printList(head);
    return 0;
}
```

**Output**

```cpp
43->65->12->46->68->85->59->85->37
6->3->6->4->2->0->1->0->0
```

我们的算法的空间复杂度是 O(n)，因为我们将元素存储在 PBDS，并散列计数。时间复杂度为 O(n*log(n))，因为 PBDS 的 insert 和 order_of_key 使用 log(n)，哈希映射采用 O(1)。