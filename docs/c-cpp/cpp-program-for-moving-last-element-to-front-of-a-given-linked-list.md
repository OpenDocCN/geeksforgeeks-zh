# 将最后一个元素移到给定链表前面的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-将最后一个元素移动到给定链表前面的程序/](https://www.geeksforgeeks.org/cpp-program-for-moving-last-element-to-front-of-a-given-linked-list/)

编写一个函数，在给定的单链表中把最后一个元素移到前面。例如，如果给定的链表是 1->2->3->4->5，那么函数应该将链表改为 5->1->2->3->4。
**算法:**
遍历列表直到最后一个节点。使用两个指针:一个存储最后一个节点的地址，另一个存储第二个最后一个节点的地址。循环结束后，执行以下操作。

1.  将倒数第二个设为最后一个(倒数第二个->下一个=空)。
2.  将倒数第二个设置为标题(最后->下一个= *head_ref)。
3.  将最后一个作为标题(*head_ref =最后一个)。

## C++

```cpp
/* C++ Program to move last element 
   to front in a given linked list */
#include <bits/stdc++.h>
using namespace std;

// A linked list node 
class Node 
{ 
    public:
    int data; 
    Node *next; 
}; 

/* We are using a double pointer
   head_ref here because we change 
   head of the linked list inside 
   this function.*/
void moveToFront(Node **head_ref) 
{ 
    /* If linked list is empty, or 
       it contains only one node, 
       then nothing needs to be done,
       simply return */
    if (*head_ref == NULL || 
       (*head_ref)->next == NULL) 
        return; 

    /* Initialize second last
       and last pointers */
    Node *secLast = NULL; 
    Node *last = *head_ref; 

    /* After this loop secLast contains
       address of second last node and 
       last contains address of last node 
       in Linked List */
    while (last->next != NULL) 
    { 
        secLast = last; 
        last = last->next; 
    } 

    // Set the next of second last as NULL 
    secLast->next = NULL; 

    // Set next of last as head node 
    last->next = *head_ref; 

    /* Change the head pointer
       to point to last node now */
    *head_ref = last; 
} 

// UTILITY FUNCTIONS 
/* Function to add a node 
   at the beginning of Linked List */
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

    // Move the head to point to the 
    // new node 
    (*head_ref) = new_node; 
} 

/* Function to print nodes in a 
   given linked list */
void printList(Node *node) 
{ 
    while(node != NULL) 
    { 
        cout << node->data << " "; 
        node = node->next; 
    } 
} 

// Driver code 
int main() 
{ 
    Node *start = NULL; 

    /* The constructed linked list is: 
       1->2->3->4->5 */
    push(&start, 5); 
    push(&start, 4); 
    push(&start, 3); 
    push(&start, 2); 
    push(&start, 1); 

    cout << 
    "Linked list before moving last to front"; 
    printList(start); 

    moveToFront(&start); 

    cout << 
    "Linked list after removing last to front"; 
    printList(start); 

    return 0; 
} 
// This code is contributed by rathbhupendra
```

**输出:**

```cpp
Linked list before moving last to front 
1 2 3 4 5 
Linked list after removing last to front 
5 1 2 3 4
```

**时间复杂度:** O(n)，其中 n 是给定链表中的节点数。

详情请参考完整文章[将最后一个元素移到给定链表](https://www.geeksforgeeks.org/move-last-element-to-front-of-a-given-linked-list/)的前面！