# 给定单链表交替拆分的 C 程序-集合 1

> 原文:[https://www . geesforgeks . org/c-program-for-alternative-split-of-给定-single-link-list-set-1/](https://www.geeksforgeeks.org/c-program-for-alternating-split-of-a-given-singly-linked-list-set-1/)

编写一个函数 AlternatingSplit()，该函数取一个列表，并将其节点划分为两个较小的列表“a”和“b”。子列表应该由原始列表中的交替元素组成。因此，如果原始列表是 0->1->0->1->0->1，那么一个子列表应该是 0->0->0，另一个应该是 1->1->1。

**方法 1(简单):**
最简单的方法是遍历源列表，从源中拉出节点，并交替将其放在“a”和“b”的前面(或开头)。唯一奇怪的是，节点的顺序与源列表中的顺序相反。方法 2 通过跟踪子列表中的最后一个节点在末尾插入节点。

## C

```cpp
/* C Program to alternatively split a 
   linked list into two halves */
#include<stdio.h>
#include<stdlib.h>
#include<assert.h>

// Link list node 
struct Node
{
    int data;
    struct Node* next;
};

/* Pull off the front node of the 
   source and put it in dest */
void MoveNode(struct Node** destRef, 
              struct Node** sourceRef) ;

/* Given the source list, split its nodes 
   into two shorter lists. If we number the 
   elements 0, 1, 2, ... then all the even 
   elements should go in the first list, and 
   all the odd elements in the second. The 
   elements in the new lists may be in any order. */
void AlternatingSplit(struct Node* source, 
                      struct Node** aRef, 
                      struct Node** bRef) 
{
  /* Split the nodes of source to 
     these 'a' and 'b' lists */
  struct Node* a = NULL; 
  struct Node* b = NULL;

  struct Node* current = source;
  while (current != NULL) 
  {
    // Move a node to list 'a' 
    MoveNode(&a, &t); 
    if (current != NULL) 
    {
       // Move a node to list 'b' 
       MoveNode(&b, &t); 
    }
  }
  *aRef = a;
  *bRef = b;
}

/* Take the node from the front of the source, 
   and move it to the front of the dest. It is 
   an error to call this with the source list 
   empty.    
   Before calling MoveNode():
   source == {1, 2, 3}   
   dest == {1, 2, 3}      
   After calling MoveNode():
   source == {2, 3}      
   dest == {1, 1, 2, 3} */
void MoveNode(struct Node** destRef, 
              struct Node** sourceRef) 
{
  // The front source node  
  struct Node* newNode = *sourceRef; 
  assert(newNode != NULL);

  // Advance the source pointer 
  *sourceRef = newNode->next;

  // Link the old dest off the 
  // new node 
  newNode->next = *destRef; 

  // Move dest to point to the 
  // new node 
  *destRef = newNode; 
}

// Utility Functions
/* Function to insert a node at the 
   beginning of the linked list */
void push(struct node** head_ref, 
          int new_data)
{
  // Allocate node 
  struct Node* new_node =
         (struct Node*) malloc(sizeof(struct Node));

  // Put in the data  
  new_node->data = new_data;

  // Link the old list off the 
  // new node 
  new_node->next = (*head_ref);     

  // Move the head to point to 
  // the new node 
  (*head_ref) = new_node;
}

/* Function to print nodes in a 
   given linked list */
void printList(struct Node *node)
{
  while(node != NULL)
  {
   printf("%d ", node->data);
   node = node->next;
  }
} 

// Driver code
int main()
{
  // Start with the empty list 
  struct Node* head = NULL;
  struct Node* a = NULL;
  struct Node* b = NULL;  

  /* Let us create a sorted linked list 
     to test the functions
     Created linked list will be 
     0->1->2->3->4->5 */
  push(&head, 5);
  push(&head, 4);
  push(&head, 3);
  push(&head, 2);
  push(&head, 1);                                    
  push(&head, 0);  

  printf("
  Original linked List:  ");
  printList(head); 

  // Remove duplicates from linked list 
  AlternatingSplit(head, &a, &b); 

  printf("
  Resultant Linked List 'a' ");
  printList(a);            

  printf("
  Resultant Linked List 'b' ");
  printList(b);            

  getchar();
  return 0;
}
```

**输出:**

```cpp
Original linked List: 0 1 2 3 4 5 
Resultant Linked List 'a' : 4 2 0 
Resultant Linked List 'b' : 5 3 1
```

**时间复杂度:** O(n)，其中 n 是给定链表中的节点数。

**方法 2(使用虚拟节点):**
这里有一种替代方法，它以与源列表相同的顺序构建子列表。代码在构建“a”和“b”列表时使用临时伪标题节点。每个子列表都有一个指向其当前最后一个节点的“尾部”指针，这样新节点就可以很容易地附加到每个列表的末尾。虚拟节点给尾部指针一些初始指向的东西。在这种情况下，虚拟节点是有效的，因为它们是临时的，并在堆栈中分配。或者，可以使用本地“引用指针”(总是指向列表中的最后一个指针，而不是最后一个节点)来避免虚拟节点。

## C

```cpp
void AlternatingSplit(struct Node* source, 
                      struct Node** aRef, 
                      struct Node** bRef) 
{
  struct Node aDummy;

  // Points to the last node in 'a' 
  struct Node* aTail = &aDummy; 
  struct Node bDummy;

  // Points to the last node in 'b' 
  struct Node* bTail = &bDummy; 
  struct Node* current = source;
  aDummy.next = NULL;
  bDummy.next = NULL;
  while (current != NULL) 
  {
    // Add at 'a' tail 
    MoveNode(&(aTail->next), &t);

    // Advance the 'a' tail 
    aTail = aTail->next; 
    if (current != NULL) 
    {
      MoveNode(&(bTail->next), &t);
      bTail = bTail->next;
    }
  }
  *aRef = aDummy.next;
  *bRef = bDummy.next;
}
```

**时间复杂度:** O(n)，其中 n 是给定链表中的节点数。
来源:[http://cslibrary.stanford.edu/105/LinkedListProblems.pdf](http://cslibrary.stanford.edu/105/LinkedListProblems.pdf)
更多详情请参考完整文章[给定单链表的交替拆分|集合 1](https://www.geeksforgeeks.org/alternating-split-of-a-given-singly-linked-list/) ！