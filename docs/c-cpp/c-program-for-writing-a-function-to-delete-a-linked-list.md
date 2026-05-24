# 编写删除链表函数的 C 程序

> 原文:[https://www . geesforgeks . org/c-写程序-函数-删除-链表/](https://www.geeksforgeeks.org/c-program-for-writing-a-function-to-delete-a-linked-list/)

**C 的算法:**
遍历链表，逐个删除所有节点。这里的要点是，如果当前指针被删除，不要访问当前指针的下一个指针。

**实施:**

## C

```cpp
// C program to delete a linked list
#include<stdio.h>
#include<stdlib.h>
#include<assert.h>

// Link list node 
struct Node
{
    int data;
    struct Node* next;
};

// Function to delete the entire 
// linked list 
void deleteList(struct Node** head_ref)
{
   // define head_ref to get the real head
   struct Node* current = *head_ref;
   struct Node* next;

   while (current != NULL) 
   {
       next = current->next;
       free(current);
       current = next;
   }

   // Define head_ref to affect the real 
   // head back in the caller. 
   *head_ref = NULL;
}

/* Given a reference (pointer to pointer) to 
   the head of a list and an int, push a new 
   node on the front of the list. */
void push(struct Node** head_ref, 
          int new_data)
{
    // Allocate node 
    struct Node* new_node =
           (struct Node*) malloc(sizeof(struct Node));

    // Put in the data  
    new_node->data  = new_data;

    // Link the old list off the new node 
    new_node->next = (*head_ref);

    // Move the head to point to the new node 
    (*head_ref)    = new_node;
}

// Driver code
int main()
{
    // Start with the empty list 
    struct Node* head = NULL;

    // Use push() to construct list
    // 1->12->1->4->1  
    push(&head, 1);
    push(&head, 4);
    push(&head, 1); 
    push(&head, 12);
    push(&head, 1);   

    printf("Deleting linked list");
    deleteList(&head);  

    printf("Linked list deleted");
}
```

**输出:**

```cpp
Deleting linked list
Linked list deleted
```

**时间复杂度:**O(n)
T3】辅助空间: O(1)

更多详情请参考[写函数删除链表](https://www.geeksforgeeks.org/write-a-function-to-delete-a-linked-list/)整篇文章！