# C 程序检查两个链表是否相同

> 原文:[https://www . geesforgeks . org/c-程序检查两个链表是否相同/](https://www.geeksforgeeks.org/c-program-to-check-if-two-linked-lists-are-identical/)

当两个链表具有相同的数据并且数据的排列也相同时，它们是相同的。例如，链表 a (1->2->3)和 b(1->2->3)是相同的。。编写一个函数来检查给定的两个链表是否相同。

**方法 1(迭代):**
要确定两个列表是否相同，我们需要同时遍历两个列表，遍历时需要比较数据。

## C

```cpp
// An iterative C program to check if 
// two linked lists are
// identical or not
#include<stdio.h>
#include<stdlib.h>
#include<stdbool.h>

// Structure for a linked list node 
struct Node
{
    int data;
    struct Node *next;
};

/* Returns true if linked lists a and b 
   are identical, otherwise false */
bool areIdentical(struct Node *a, 
                  struct Node *b)
{
    while (a != NULL && b != NULL)
    {
        if (a->data != b->data)
            return false;

        /* If we reach here, then a and b 
           are not NULL and their data is 
           same, so move to next nodes in 
           both lists */
        a = a->next;
        b = b->next;
    }

    // If linked lists are identical, then 
    // 'a' and 'b' must be NULL at this point.
    return (a == NULL && b == NULL);
}

/* UTILITY FUNCTIONS TO TEST fun1() 
   and fun2() */
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

    // Link the old list off the new node 
    new_node->next = (*head_ref);

    // Move the head to point to the 
    // new node 
    (*head_ref) = new_node;
}

// Driver code
int main()
{
    /* The constructed linked lists are :
       a: 3->2->1
       b: 3->2->1 */
    struct Node *a = NULL;
    struct Node *b = NULL;
    push(&a, 1);
    push(&a, 2);
    push(&a, 3);
    push(&b, 1);
    push(&b, 2);
    push(&b, 3);

    areIdentical(a, b)? printf("Identical"):
                        printf("Not identical");
    return 0;
}
```

**输出:**

```cpp
Identical
```

**方法 2(递归):**
递归求解代码比迭代代码干净得多。然而，您可能不想将递归版本用于生产代码，因为它将使用与列表长度成比例的堆栈空间。

## C

```cpp
// A recursive C function to check if 
// two linked lists are identical or not
bool areIdentical(struct Node *a, 
                  struct Node *b)
{
    // If both lists are empty
    if (a == NULL && b == NULL)
       return true;

    // If both lists are not empty, then 
    // data of current nodes must match, 
    // and same should be recursively true 
    // for rest of the nodes.
    if (a != NULL && b != NULL)
       return (a->data == b->data) &&
              areIdentical(a->next, b->next);

    // If we reach here, then one of the lists
    // is empty and other is not
    return false;
}
```

**时间复杂度:** O(n)对于迭代和递归版本。n 是 a 和 b 中较小列表的长度。

更多详情请参考[完全相同链表](https://www.geeksforgeeks.org/identical-linked-lists/)的完整文章！