# 给定链表成对交换元素的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-程序对成对交换给定链表的元素/](https://www.geeksforgeeks.org/cpp-program-for-pairwise-swapping-elements-of-a-given-linked-list/)

给定一个单链表，编写一个成对交换元素的函数。

```cpp
Input: 1->2->3->4->5->6->NULL 
Output: 2->1->4->3->6->5->NULL

Input: 1->2->3->4->5->NULL 
Output: 2->1->4->3->5->NULL

Input: 1->NULL 
Output: 1->NULL 

```

例如，如果链表是 1->2->3->4->5，那么函数应该将其改为 2->1->4->3->5，如果链表是，那么函数应该将其改为。

**方法(迭代):**
从头节点开始遍历列表。同时用下一个节点的数据遍历每个节点的交换数据。
以下是上述方法的实施:

## C++

```cpp
// C++ program to pairwise swap elements
// in a given linked list
#include <bits/stdc++.h>
using namespace std;

// A linked list node
class Node 
{
    public:
    int data;
    Node* next;
};

/* Function to pairwise swap elements
   of a linked list */
void pairWiseSwap(Node* head)
{
    Node* temp = head;

    /* Traverse further only if there 
       are at-least two nodes left */
    while (temp != NULL && 
           temp->next != NULL) 
    {
        /* Swap data of node with 
           its next node's data */
        swap(temp->data,
             temp->next->data);

        // Move temp by 2 for the next pair
        temp = temp->next->next;
    }
}

/* Function to add a node at the 
   beginning of Linked List */
void push(Node** head_ref, 
          int new_data)
{
    // Allocate node 
    Node* new_node = new Node();

    // Put in the data 
    new_node->data = new_data;

    // Link the old list off the 
    // new node 
    new_node->next = (*head_ref);

    /* Move the head to point 
       to the new node */
    (*head_ref) = new_node;
}

/* Function to print nodes
   in a given linked list */
void printList(Node* node)
{
    while (node != NULL) 
    {
        cout << node->data << " ";
        node = node->next;
    }
}

// Driver Code
int main()
{
    Node* start = NULL;

    /* The constructed linked list is: 
       1->2->3->4->5 */
    push(&start, 5);
    push(&start, 4);
    push(&start, 3);
    push(&start, 2);
    push(&start, 1);

    cout << "Linked list " << 
            "before calling pairWiseSwap()";
    printList(start);

    pairWiseSwap(start);

    cout << "Linked list " << 
            "after calling pairWiseSwap()";
    printList(start);

    return 0;
}
// This code is contributed by rathbhupendra
```

**输出:**

```cpp
Linked list before calling pairWiseSwap()
1 2 3 4 5 
Linked list after calling pairWiseSwap()
2 1 4 3 5 
```

**时间复杂度:** O(n)
更多详情请参考[给定链表](https://www.geeksforgeeks.org/pairwise-swap-elements-of-a-given-linked-list/)两两互换元素的完整文章！