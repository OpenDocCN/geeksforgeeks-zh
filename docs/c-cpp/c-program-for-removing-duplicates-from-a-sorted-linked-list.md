# 用于从排序的链表中删除重复项的程序

> 原文:[https://www . geesforgeks . org/c-从排序链表中删除重复项的程序/](https://www.geeksforgeeks.org/c-program-for-removing-duplicates-from-a-sorted-linked-list/)

编写一个函数，接受按非递减顺序排序的列表，并从列表中删除任何重复的节点。该列表只能遍历一次。
例如，如果链接列表是 11->11->11->21->43->43->60，则 removeDuplicates()应该将列表转换为 11- > 21- > 43- > 60。

**算法:**
从头(或开始)节点遍历列表。遍历时，将每个节点与其下一个节点进行比较。如果下一个节点的数据与当前节点相同，则删除下一个节点。在删除节点之前，我们需要存储节点的下一个指针

**实现:**
removeDuplicates()之外的函数只是创建一个链表并测试 remove duplicates()。

## C

```cpp
// C Program to remove duplicates 
// from a sorted linked list 
#include<stdio.h>
#include<stdlib.h>

// Link list node
struct Node
{
    int data;
    struct Node* next;
};

// The function removes duplicates 
// from a sorted list 
void removeDuplicates(struct Node* head)
{
    // Pointer to traverse the linked list 
    struct Node* current = head;

    // Pointer to store the next pointer 
    // of a node to be deleted
    struct Node* next_next; 

    // Do nothing if the list is empty 
    if (current == NULL) 
       return; 

    // Traverse the list till last node 
    while (current->next != NULL) 
    {
       // Compare current node with next node 
       if (current->data == current->next->data) 
       {
           // The sequence of steps is important
           next_next = current->next->next;
           free(current->next);
           current->next = next_next;  
       }

       // This is tricky: only advance 
       // if no deletion
       else 
       {
          current = current->next; 
       }
    }
}

// UTILITY FUNCTIONS 
// Function to insert a node at the
// beginning of the linked list 
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

    // Move the head to point to the 
    // new node 
    (*head_ref) = new_node;
}

// Function to print nodes in a given 
// linked list 
void printList(struct Node *node)
{
    while (node!=NULL)
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

    /* Let us create a sorted linked list 
       to test the functions. Created 
       linked list will be 
       11->11->11->13->13->20 */
    push(&head, 20);
    push(&head, 13);
    push(&head, 13);  
    push(&head, 11);
    push(&head, 11);
    push(&head, 11);                                    

    printf(
    "Linked list before duplicate removal  ");
    printList(head); 

    // Remove duplicates from linked list 
    removeDuplicates(head); 

    printf(
    "Linked list after duplicate removal ");         
    printList(head);            

    return 0;
}
```

**输出:**

```cpp
Linked list before duplicate removal  11 11 11 13 13 20
Linked list after duplicate removal  11 13 20
```

**时间复杂度:** O(n)，其中 n 是给定链表中的节点数。

**递归方法:**

## C

```cpp
// C recursive Program to remove duplicates
// from a sorted linked list
#include<stdio.h>
#include<stdlib.h>

// Link list node 
struct Node
{
    int data;
    struct Node* next;
};

// UTILITY FUNCTIONS 
// Function to insert a node at 
// the beginning of the linked list 
void push(struct Node** head_ref, 
          int new_data)
{
    // Allocate node 
    struct Node* new_node =
           (struct Node*) malloc(sizeof(struct Node));

    // Put in the data  
    new_node->data  = new_data;

    // Link the old list off the 
    // new node 
    new_node->next = (*head_ref);     

    // Move the head to point to the 
    // new node 
    (*head_ref)    = new_node;
}

// Function to print nodes in a 
// given linked list 
void printList(struct Node *node)
{
    while (node!=NULL)
    {
       printf("%d ", node->data);
       node = node->next;
    }
} 

Node* deleteDuplicates(Node* head) 
{
    if (head == nullptr) 
        return nullptr;

    if (head->next == nullptr) 
        return head;

    if (head->data == head->next->data) 
    {
        Node *tmp;

        // If find next element duplicate, 
        // preserve the next pointer to be 
        // deleted, skip it, and then delete 
        // the stored one. Return head
        tmp = head->next;
        head->next = head->next->next;
        free(tmp);
        return deleteDuplicates(head);
    }

    else 
    {
        // if doesn't find next element duplicate, leave head 
        // and check from next element
        head->next = deleteDuplicates(head->next);
        return head;
    }
}

// Driver code
int main()
{
    // Start with the empty list 
    struct Node* head = NULL;

    /* Let us create a sorted linked list 
       to test the functions. Created 
       linked list will be 11->11->11->13->13->20 */
    push(&head, 20);
    push(&head, 13);
    push(&head, 13);  
    push(&head, 11);
    push(&head, 11);
    push(&head, 11);                                    

    printf(
    "Linked list before duplicate removal  ");
    printList(head); 

    // Remove duplicates from linked list 
    head = deleteDuplicates(head); 

    printf(
    "Linked list after duplicate removal ");         
    printList(head);            

    return 0;
}
// This code is contributed by Yogesh shukla 
```

**输出:**

```cpp
Linked list before duplicate removal  11 11 11 13 13 20
Linked list after duplicate removal  11 13 20
```

更多详情请参考[从排序链表](https://www.geeksforgeeks.org/remove-duplicates-from-a-sorted-linked-list/)中删除重复项的完整文章！