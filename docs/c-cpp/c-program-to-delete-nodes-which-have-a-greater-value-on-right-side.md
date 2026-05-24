# C 程序删除右侧数值较大的节点

> 原文:[https://www . geesforgeks . org/c-program-to-delete-节点-右侧值较大的节点/](https://www.geeksforgeeks.org/c-program-to-delete-nodes-which-have-a-greater-value-on-right-side/)

给定一个单链表，移除右边值较大的所有节点。

**示例:**

```cpp
Input: 12->15->10->11->5->6->2->3->NULL
Output: 15->11->6->3->NULL
Explanation: 12, 10, 5 and 2 have been deleted because there is a 
             greater value on the right side. When we examine 12, 
             we see that after 12 there is one node with a value 
             greater than 12 (i.e. 15), so we delete 12. When we 
             examine 15, we find no node after 15 that has a value 
             greater than 15, so we keep this node. When we go like 
             this, we get 15->6->3

Input: 10->20->30->40->50->60->NULL
Output: 60->NULL
Explanation: 10, 20, 30, 40, and 50 have been deleted because 
             they all have a greater value on the right side.

Input: 60->50->40->30->20->10->NULL
Output: No Change.

```

**方法 1(简单):**
使用两个循环。在外循环中，逐个挑选链表的节点。在内部循环中，检查是否存在其值大于拾取节点的节点。如果存在值更大的节点，则删除拾取的节点。
**时间复杂度:** O(n^2)

**方法 2(反向使用):**
感谢帕拉斯提供以下算法。
1。颠倒列表。
2。遍历反向列表。把麦克斯留到现在。如果下一个节点小于 max，则删除下一个节点，否则 max =下一个节点。
3。再次反转列表以保留原始顺序。
**时间复杂度:** O(n)
感谢 R.Srinivasan 提供下面的代码。

## C

```cpp
// C program to delete nodes which have 
// a greater value on right side
#include <stdio.h>
#include <stdlib.h>

// Structure of a linked list 
// node 
struct Node 
{
    int data;
    struct Node* next;
};

// Prototype for utility functions 
void reverseList(struct Node** headref);
void _delLesserNodes(struct Node* head);

/* Deletes nodes which have a node with 
   greater value node on left side */
void delLesserNodes(struct Node** head_ref)
{
    // 1\. Reverse the linked list 
    reverseList(head_ref);

    /* 2\. In the reversed list, delete nodes 
          which have a node with greater value 
          node on left side. Note that head node 
          is never deleted because it is the leftmost 
          node.*/
    _delLesserNodes(*head_ref);

    /* 3\. Reverse the linked list again to retain the
          original order */
    reverseList(head_ref);
}

/* Deletes nodes which have greater value 
   node(s) on left side */
void _delLesserNodes(struct Node* head)
{
    struct Node* current = head;

    // Initialize max 
    struct Node* maxnode = head;
    struct Node* temp;

    while (current != NULL && 
           current->next != NULL) 
    {
        /* If current is smaller than max, 
           then delete current */
        if (current->next->data < 
            maxnode->data) 
        {
            temp = current->next;
            current->next = temp->next;
            free(temp);
        }

        /* If current is greater than max, 
           then update max and move current */
        else 
        {
            current = current->next;
            maxnode = current;
        }
    }
}

/* Utility function to insert a 
   node at the beginning */
void push(struct Node** head_ref, 
          int new_data)
{
    struct Node* new_node = 
           (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = *head_ref;
    *head_ref = new_node;
}

/* Utility function to reverse a 
   linked list */
void reverseList(struct Node** headref)
{
    struct Node* current = *headref;
    struct Node* prev = NULL;
    struct Node* next;
    while (current != NULL) 
    {
        next = current->next;
        current->next = prev;
        prev = current;
        current = next;
    }
    *headref = prev;
}

/* Utility function to print a 
   linked list */
void printList(struct Node* head)
{
    while (head != NULL) 
    {
        printf("%d ", head->data);
        head = head->next;
    }
    printf("");
}

// Driver code
int main()
{
    struct Node* head = NULL;

    /* Create following linked list
       12->15->10->11->5->6->2->3 */
    push(&head, 3);
    push(&head, 2);
    push(&head, 6);
    push(&head, 5);
    push(&head, 11);
    push(&head, 10);
    push(&head, 15);
    push(&head, 12);

    printf("Given Linked List ");
    printList(head);

    delLesserNodes(&head);

    printf("Modified Linked List ");
    printList(head);

    return 0;
}
```

**输出:**

```cpp
Given Linked List 
12 15 10 11 5 6 2 3
Modified Linked List 
15 11 6 3
```

来源:[https://www . geeksforgeeks . org/forum/topic/Amazon-interview-question-for-software-engineer developer-about-linked-list-6](https://www.geeksforgeeks.org/forum/topic/amazon-interview-question-for-software-engineerdeveloper-about-linked-lists-6)

详情请参考[整篇文章删除右侧](https://www.geeksforgeeks.org/delete-nodes-which-have-a-greater-value-on-right-side/)数值较大的节点！