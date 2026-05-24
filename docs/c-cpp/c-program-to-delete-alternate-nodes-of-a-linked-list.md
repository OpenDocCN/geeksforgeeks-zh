# C 程序删除链表的备用节点

> 原文:[https://www . geesforgeks . org/c-program-to-delete-alternate-nodes-of-a-link-list/](https://www.geeksforgeeks.org/c-program-to-delete-alternate-nodes-of-a-linked-list/)

给定一个单链表，从第二个节点开始删除它的所有替换节点。例如，如果给定的链表是 1->2->3->4->5，那么你的函数应该把它转换成 1->3->5，如果给定的链表是 1->2->3->4，那么把它转换成 1->3。

**方法 1(迭代):**
跟踪要删除的节点的前一个。首先，更改上一个节点的下一个链接，并迭代移动到下一个节点。

## C

```cpp
// C program to remove alternate nodes 
// of a linked list
#include<stdio.h>
#include<stdlib.h>

// A linked list node 
struct Node
{
    int data;
    struct Node *next;
};

// Deletes alternate nodes of a list 
// starting with head 
void deleteAlt(struct Node *head)
{
    if (head == NULL)
        return;

    // Initialize prev and node to 
    // be deleted 
    struct Node *prev = head;
    struct Node *node = head->next;

    while (prev != NULL && 
           node != NULL)
    {
        // Change next link of previous 
        // node 
        prev->next = node->next;

        // Free memory 
        free(node);

        // Update prev and node 
        prev = prev->next;
        if (prev != NULL)
            node = prev->next;
    }
}

// UTILITY FUNCTIONS TO TEST 
// fun1() and fun2() 
/* Given a reference (pointer to pointer) 
   to the head of a list and an int, push 
   a new node on the front of the list. */
void push(struct Node** head_ref, 
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

// Function to print nodes in a 
// given linked list 
void printList(struct Node *node)
{
    while (node != NULL)
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

    /* Using push() to construct list
       1->2->3->4->5  */
    push(&head, 5);
    push(&head, 4);
    push(&head, 3);
    push(&head, 2);
    push(&head, 1);

    printf("\nList before calling deleteAlt() \n");
    printList(head);

    deleteAlt(head);

    printf("\nList after calling deleteAlt() \n");
    printList(head);
    return 0;
}
```

**输出:**

```cpp
List before calling deleteAlt() 
1 2 3 4 5 
List after calling deleteAlt() 
1 3 5 
```

**时间复杂度:** O(n)，其中 n 是给定链表中的节点数。

**方法 2(递归):**
递归代码使用与方法 1 相同的方法。递归代码简单而简短，但会导致 O(n)个递归函数调用大小为 n 的链表。

## C

```cpp
// Deletes alternate nodes of a list 
// starting with head 
void deleteAlt(struct Node *head)
{
    if (head == NULL)
        return;

    struct Node *node = head->next;

    if (node == NULL)
        return;

    // Change the next link of head 
    head->next = node->next;

    // Free memory allocated for node 
    free(node);

    // Recursively call for the new 
    // next of head 
    deleteAlt(head->next);
}
```

**时间复杂度:** O(n)

更多详情请参考[删除链表备用节点](https://www.geeksforgeeks.org/delete-alternate-nodes-of-a-linked-list/)整篇文章！