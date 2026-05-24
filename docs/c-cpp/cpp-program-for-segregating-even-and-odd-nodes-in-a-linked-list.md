# 用于分离链表中偶数和奇数节点的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-隔离链表中奇偶节点的程序/](https://www.geeksforgeeks.org/cpp-program-for-segregating-even-and-odd-nodes-in-a-linked-list/)

给定一个整数链表，编写一个函数来修改链表，使得在修改后的链表中，所有偶数出现在所有奇数之前。此外，保持偶数和奇数的顺序相同。
**例:**

```cpp
Input: 17->15->8->12->10->5->4->1->7->6->NULL
Output: 8->12->10->4->6->17->15->5->1->7->NULL

Input: 8->12->10->5->4->1->6->NULL
Output: 8->12->10->4->6->5->1->NULL

// If all numbers are even then do not change the list
Input: 8->12->10->NULL
Output: 8->12->10->NULL

// If all numbers are odd then do not change the list
Input: 1->3->5->7->NULL
Output: 1->3->5->7->NULL
```

**方法 1:**
思路是获取指向列表最后一个节点的指针。然后从头节点开始遍历列表，并将奇数值节点从它们的当前位置移动到列表的末尾。
感谢浮躁小子提出这个方法。
**算法:**

1.  获取指向最后一个节点的指针。
2.  将所有奇数节点移动到最后。
    *   考虑第一个偶数节点之前的所有奇数节点，并将它们移动到末尾。
    *   将头指针更改为指向第一个偶数节点。
    *   考虑第一个偶数节点之后的所有奇数节点，并将它们移动到最后。

## C++

```cpp
// C++ program to segregate even and
// odd nodes in a Linked List 
#include <bits/stdc++.h>
using namespace std;

// A node of the singly linked list
class Node 
{ 
    public:
    int data; 
    Node *next; 
}; 

void segregateEvenOdd(Node **head_ref) 
{ 
    Node *end = *head_ref; 
    Node *prev = NULL; 
    Node *curr = *head_ref; 

    // Get pointer to the last node 
    while (end->next != NULL) 
        end = end->next; 

    Node *new_end = end; 

    /* Consider all odd nodes before 
       the first even node and move 
       then after end */
    while (curr->data % 2 != 0 && 
           curr != end) 
    { 
        new_end->next = curr; 
        curr = curr->next; 
        new_end->next->next = NULL; 
        new_end = new_end->next; 
    } 

    // 10->8->17->17->15 
    /* Do following steps only if 
       there is any even node */
    if (curr->data%2 == 0) 
    { 
        /* Change the head pointer to 
           point to first even node */
        *head_ref = curr; 

        /* Now current points to
           the first even node */
        while (curr != end) 
        { 
            if ( (curr->data) % 2 == 0 ) 
            { 
                prev = curr; 
                curr = curr->next; 
            } 
            else
            { 
                /* Break the link between
                   prev and current */
                prev->next = curr->next; 

                // Make next of curr as NULL 
                curr->next = NULL; 

                // Move curr to end 
                new_end->next = curr; 

                // Make curr as new end of list 
                new_end = curr; 

                /* Update current pointer to
                   next of the moved node */
                curr = prev->next; 
            } 
        } 
    } 

    /* We must have prev set before  
       executing lines following this 
       statement */
    else prev = curr; 

    /* If there are more than 1 odd nodes 
       and end of original list is odd then 
       move this node to end to maintain 
       same order of odd numbers in modified 
       list */
    if (new_end != end && 
       (end->data) % 2 != 0) 
    { 
        prev->next = end->next; 
        end->next = NULL; 
        new_end->next = end; 
    } 
    return; 
} 

// UTILITY FUNCTIONS 
/* Function to insert a node at 
   the beginning */
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

    // Move the head to point to 
    // the new node 
    (*head_ref) = new_node; 
} 

// Function to print nodes in a 
// given linked list 
void printList(Node *node) 
{ 
    while (node != NULL) 
    { 
        cout << node->data <<" "; 
        node = node->next; 
    } 
} 

// Driver code
int main() 
{ 
    // Start with the empty list 
    Node* head = NULL; 

    /* Let us create a sample 
       linked list as following 
       0->2->4->6->8->10->11 */
    push(&head, 11); 
    push(&head, 10); 
    push(&head, 8); 
    push(&head, 6); 
    push(&head, 4); 
    push(&head, 2); 
    push(&head, 0); 

    cout << "Original Linked list "; 
    printList(head); 

    segregateEvenOdd(&head); 

    cout << "Modified Linked list "; 
    printList(head); 

    return 0; 
} 
// This code is contributed by rathbhupendra
```

**输出:**

```cpp
 Original Linked list 0 2 4 6 8 10 11
 Modified Linked list 0 2 4 6 8 10 11
```

**时间复杂度:** O(n)

**方法二:**
思路是把链表一分为二:一个包含所有偶数节点，另一个包含所有奇数节点。最后，在偶数节点链表之后附加奇数节点链表。
要拆分链表，遍历原始链表，将所有奇数节点移动到所有奇数节点的单独链表中。在循环结束时，原始列表将包含所有偶数节点，奇数节点列表将包含所有奇数节点。为了保持所有节点的顺序相同，我们必须在奇数节点列表的末尾插入所有奇数节点。为了在恒定时间内做到这一点，我们必须跟踪奇数节点列表中的最后一个指针。

## C++

```cpp
// CPP program to segregate even and 
// odd nodes in a Linked List
#include <stdio.h>
#include <stdlib.h>

// A node of the singly linked list 
struct Node
{
    int data;
    struct Node *next;
};

// Function to segregate even and 
// odd nodes.
void segregateEvenOdd(struct Node **head_ref)
{
    // Starting node of list having 
    // even values.
    Node *evenStart = NULL;

    // Ending node of even values list.
    Node *evenEnd = NULL;

    // Starting node of odd values list.
    Node *oddStart = NULL;

    // Ending node of odd values list.
    Node *oddEnd = NULL;

    // Node to traverse the list.
    Node *currNode = *head_ref;

    while(currNode != NULL)
    {
        int val = currNode -> data;

        // If current value is even, add
        // it to even values list.
        if(val % 2 == 0) 
        {
            if(evenStart == NULL)
            {
                evenStart = currNode;
                evenEnd = evenStart;
            }

            else
            {
                evenEnd -> next = currNode;
                evenEnd = evenEnd -> next;
            }
        } 

        // If current value is odd, add 
        // it to odd values list.
        else
        {
            if(oddStart == NULL)
            {
                oddStart = currNode;
                oddEnd = oddStart;
            }
            else
            {
                oddEnd -> next = currNode;
                oddEnd = oddEnd -> next;
            }
        }

        // Move head pointer one step in 
        // forward direction
        currNode = currNode -> next;    
    }

    // If either odd list or even list 
    // is empty, no change is required 
    // as all elements are either even 
    // or odd.
    if(oddStart == NULL || 
       evenStart == NULL)
    {
        return;
    }

    // Add odd list after even list.     
    evenEnd -> next = oddStart;
    oddEnd -> next = NULL;

    // Modify head pointer to 
    // starting of even list.
    *head_ref = evenStart;
}

// UTILITY FUNCTIONS 
/* Function to insert a node at 
   the beginning */
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

    // Move the head to point to the
    // new node 
    (*head_ref) = new_node;
}

/* Function to print nodes in a 
   given linked list */
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

    /* Let us create a sample 
       linked list as following
       0->1->4->6->9->10->11 */
    push(&head, 11);
    push(&head, 10);
    push(&head, 9);
    push(&head, 6);
    push(&head, 4);
    push(&head, 1);
    push(&head, 0);

    printf("Original Linked list ");
    printList(head);

    segregateEvenOdd(&head);

    printf("Modified Linked list ");
    printList(head);

    return 0;
}
// This code is contributed by NIKHIL JINDAL.
```

**输出:**

```cpp
Origional Linked List
0 1 4 6 9 10 11 
Modified Linked List
0 4 6 10 1 9 11 
```

**时间复杂度:** O(n)
更多详情请参考完整文章[在链表中隔离奇偶节点](https://www.geeksforgeeks.org/segregate-even-and-odd-elements-in-a-linked-list/)！