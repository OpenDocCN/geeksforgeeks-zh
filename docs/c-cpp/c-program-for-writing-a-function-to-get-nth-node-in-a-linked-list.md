# 编写函数获取链表中第 n 个节点的 C 程序

> 原文:[https://www . geesforgeks . org/c-写程序-函数-获取链表中的第 n 个节点/](https://www.geeksforgeeks.org/c-program-for-writing-a-function-to-get-nth-node-in-a-linked-list/)

编写一个 GetNth()函数，该函数接受一个链表和一个整数索引，并返回存储在该索引位置的节点中的数据值。

**例:**

```cpp
Input:  1->10->30->14,  index = 2
Output: 30  
The node at index 2 is 30
```

**算法:**

```cpp
1\. Initialize count = 0
2\. Loop through the link list
     a. If count is equal to the passed index then return current
         node
     b. Increment count
     c. Change current to point to next of the current.
```

**实施:**

## C

```cpp
// C program to find n'th
// node in linked list
#include <assert.h>
#include <stdio.h>
#include <stdlib.h>

// Link list node
struct Node 
{
    int data;
    struct Node* next;
};

/* Given a reference (pointer to
   pointer) to the head of a list
   and an int, push a new node on
   the front of the list. */
void push(struct Node** head_ref, 
          int new_data)
{
    // Allocate node
    struct Node* new_node = 
           (struct Node*)malloc(sizeof(struct Node));

    // Put in the data
    new_node->data = new_data;

    // Link the old list
    // off the new node
    new_node->next = (*head_ref);

    // Move the head to point
    // to the new node
    (*head_ref) = new_node;
}

// Takes head pointer of
// the linked list and index
// as arguments and return
// data at index
int GetNth(struct Node* head, 
           int index)
{
    struct Node* current = head;

    // The index of the node we're 
    // currently looking at
    int count = 0;
    while (current != NULL) 
    {
        if (count == index)
            return (current->data);
        count++ ;
        current = current->next;
    }

    /* If we get to this line, the 
       caller was asking for a 
       non-existent element so we 
        assert fail */
    assert(0);
}

// Driver Code
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

    // Check the count function
    printf("Element at index 3 is %d", 
            GetNth(head, 3));
    getchar();
}
```

**输出:**

```cpp
Element at index 3 is 4
```

**时间复杂度:** O(n)

详情请参考[写函数获取链表](https://www.geeksforgeeks.org/write-a-function-to-get-nth-node-in-a-linked-list/)中第 n 个节点的完整文章！