# 用于反转单链表中交替 K 个节点的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-程序-换向-交替-单链表中的 k 个节点/](https://www.geeksforgeeks.org/cpp-program-for-reversing-alternate-k-nodes-in-a-singly-linked-list/)

给定一个链表，编写一个函数以高效的方式反转每一个交替的 k 个节点(其中 k 是函数的输入)。给出你的算法的复杂性。

**示例:**

```cpp
Inputs:   1->2->3->4->5->6->7->8->9->NULL and k = 3
Output:   3->2->1->4->5->6->9->8->7->NULL. 
```

**方法 1(处理 2k 个节点并递归调用列表的其余部分):**
这个方法基本上是[这篇](https://www.geeksforgeeks.org/reverse-a-list-in-groups-of-given-size/)帖子中讨论的方法的扩展。

```cpp
kAltReverse(struct node *head, int k)
  1)  Reverse first k nodes.
  2)  In the modified list head points to the kth node.  So change next 
       of head to (k+1)th node
  3)  Move the current pointer to skip next k nodes.
  4)  Call the kAltReverse() recursively for rest of the n - 2k nodes.
  5)  Return new head of the list.
```

## C++

```cpp
// C++ program to reverse alternate
// k nodes in a linked list
#include <bits/stdc++.h>
using namespace std;

// Link list node 
class Node 
{ 
    public:
    int data; 
    Node* next; 
}; 

/* Reverses alternate k nodes and 
   returns the pointer to the new 
   head node */
Node *kAltReverse(Node *head, int k) 
{ 
    Node* current = head; 
    Node* next; 
    Node* prev = NULL; 
    int count = 0; 

    /* 1) reverse first k nodes of the 
       linked list */
    while (current != NULL && count < k) 
    { 
    next = current->next; 
    current->next = prev; 
    prev = current; 
    current = next; 
    count++ ; 
    } 

    /* 2) Now head points to the kth node. 
       So change next  of head to (k+1)th node*/
    if(head != NULL) 
    head->next = current; 

    /* 3) We do not want to reverse next k 
       nodes. So move the current 
       pointer to skip next k nodes */
    count = 0; 
    while(count < k-1 && 
          current != NULL ) 
    { 
    current = current->next; 
    count++ ; 
    } 

    /* 4) Recursively call for the list 
       starting from current->next. And make
       rest of the list as next of first node */
    if(current != NULL) 
    current->next = kAltReverse(current->next, k); 

    /* 5) prev is new head of the input list */
    return prev; 
} 

// UTILITY FUNCTIONS 
// Function to push a node 
void push(Node** head_ref, 
          int new_data) 
{ 
    // Allocate node 
    Node* new_node = new Node();

    //  Put in the data 
    new_node->data = new_data; 

    // Link the old list off the 
    // new node 
    new_node->next = (*head_ref);     

    // Move the head to point to the 
    // new node 
    (*head_ref) = new_node; 
} 

// Function to print linked list 
void printList(Node *node) 
{ 
    int count = 0; 
    while(node != NULL) 
    { 
        cout<<node->data<<" "; 
        node = node->next; 
        count++ ; 
    } 
} 

// Driver code
int main(void) 
{ 
    // Start with the empty list 
    Node* head = NULL; 
    int i; 

    // Create a list
    // 1->2->3->4->5...... ->20 
    for(i = 20; i > 0; i--) 
    push(&head, i); 

    cout << "Given linked list "; 
    printList(head); 
    head = kAltReverse(head, 3); 

    cout << "Modified Linked list "; 
    printList(head); 
    return(0); 
} 
// This code is contributed by rathbhupendra
```

**输出:**

```cpp
Given linked list
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
Modified Linked list
3 2 1 4 5 6 9 8 7 10 11 12 15 14 13 16 17 18 20 19
```

**时间复杂度:** O(n)

**方法 2(处理 k 个节点并递归调用列表的其余部分):**
方法 1 反转第一个 k 个节点，然后将指针移动到前面的 k 个节点。所以方法 1 使用两个 while 循环，在一次递归调用中处理 2k 个节点。

这个方法在递归调用中只处理 k 个节点。它使用第三个 bool 参数 b 来决定是反转 k 个元素还是简单地移动指针。

```cpp
_kAltReverse(struct node *head, int k, bool b)
  1)  If b is true, then reverse first k nodes.
  2)  If b is false, then move the pointer k nodes ahead.
  3)  Call the kAltReverse() recursively for rest of the n - k nodes and link 
       rest of the modified list with end of first k nodes. 
  4)  Return new head of the list.
```

## C++

```cpp
// C++ program to implement 
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Link list node 
class node 
{ 
    public:
    int data; 
    node* next; 
}; 

// Helper function for kAltReverse() 
node * _kAltReverse(node *node, 
                    int k, bool b); 

// Alternatively reverses the given 
// linked list in groups of given size k.
node *kAltReverse(node *head, int k) 
{ 
    return _kAltReverse(head, k, true); 
} 

/* Helper function for kAltReverse().  
   It reverses k nodes of the list only if 
   the third parameter b is passed as true, 
   otherwise moves the pointer k nodes ahead
   and recursively calls itself */
node * _kAltReverse(node *Node, int k, bool b) 
{ 
    if(Node == NULL) 
        return NULL; 

    int count = 1; 
    node *prev = NULL; 
    node *current = Node; 
    node *next; 

    /* The loop serves two purposes 
        1) If b is true, 
           then it reverses the k nodes 
        2) If b is false, 
           then it moves the current pointer */
    while(current != NULL && count <= k) 
    { 
        next = current->next; 

        // Reverse the nodes only if b is true
        if(b == true) 
            current->next = prev; 

        prev = current; 
        current = next; 
        count++ ; 
    } 

    /* 3) If b is true, then the node is the kth node. 
        So attach the rest of the list after the node. 
        4) After attaching, return the new head */
    if(b == true) 
    { 
        Node->next = _kAltReverse(current, k, !b); 
        return prev;         
    } 

    /* If b is not true, then attach 
       rest of the list after prev.
       So attach the rest of the list 
       after prev */
    else
    { 
        prev->next = 
            _kAltReverse(current, k, !b); 
        return Node;     
    } 
} 

// UTILITY FUNCTIONS 
// Function to push a node 
void push(node** head_ref,
          int new_data) 
{ 
    // Allocate node 
    node* new_node = new node();

    // Put in the data 
    new_node->data = new_data; 

    // Link the old list off the 
    // new node 
    new_node->next = (*head_ref); 

    // Move the head to point to 
    // the new node 
    (*head_ref) = new_node; 
} 

// Function to print linked list 
void printList(node *node) 
{ 
    int count = 0; 
    while(node != NULL) 
    { 
        cout << node->data << " "; 
        node = node->next; 
        count++ ; 
    } 
} 

// Driver Code
int main(void) 
{ 
    // Start with the empty list 
    node* head = NULL; 
    int i; 

    // Create a list 
    // 1->2->3->4->5...... ->20 
    for(i = 20; i > 0; i--) 
    push(&head, i); 

    cout << "Given linked list "; 
    printList(head); 
    head = kAltReverse(head, 3); 

    cout << "Modified Linked list "; 
    printList(head); 
    return(0); 
} 
// This code is contributed by rathbhupendra
```

**输出:**

```cpp
Given linked list
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
Modified Linked list
3 2 1 4 5 6 9 8 7 10 11 12 15 14 13 16 17 18 20 19
```

**时间复杂度:** O(n)

更多详情请参考[反向单链表中交替 K 节点](https://www.geeksforgeeks.org/reverse-alternate-k-nodes-in-a-singly-linked-list/)整篇文章！