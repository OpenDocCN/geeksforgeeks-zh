# 编写删除链表函数的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-写程序-函数-删除-链表/](https://www.geeksforgeeks.org/cpp-program-for-writing-a-function-to-delete-a-linked-list/)

**c++ 的算法:**
遍历链表，逐个删除所有节点。这里的要点是，如果当前指针被删除，不要访问当前指针的下一个指针。

**实施:**

## C++

```cpp
// C++ program to delete a linked list
#include <bits/stdc++.h>
using namespace std;

// Link list node 
class Node 
{
    public:
    int data;
    Node* next;
};

// Function to delete the entire 
// linked list 
void deleteList(Node** head_ref)
{
    // Define head_ref to get the 
    // real head 
    Node* current = *head_ref;
    Node* next = NULL;

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

/* Given a reference (pointer to pointer) 
   to the head of a list and an int, push 
   a new node on the front of the list. */
void push(Node** head_ref, int new_data)
{
    // Allocate node 
    Node* new_node = new Node();

    // Put in the data 
    new_node->data = new_data;

    // Link the old list off the new node 
    new_node->next = (*head_ref);

    // Move the head to point to the new node 
    (*head_ref) = new_node;
}

// Driver code
int main()
{
    // Start with the empty list 
    Node* head = NULL;

    // Use push() to construct list
    // 1->12->1->4->1
    push(&head, 1);
    push(&head, 4);
    push(&head, 1);
    push(&head, 12);
    push(&head, 1);

    cout << "Deleting linked list";
    deleteList(&head);

    cout << "Linked list deleted";
}
// This code is contributed by rathbhupendra
```

**输出:**

```cpp
Deleting linked list
Linked list deleted
```