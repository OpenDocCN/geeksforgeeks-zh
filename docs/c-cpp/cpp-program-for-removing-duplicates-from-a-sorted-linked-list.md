# 用于从排序链表中删除重复项的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-从排序链表中删除重复项的程序/](https://www.geeksforgeeks.org/cpp-program-for-removing-duplicates-from-a-sorted-linked-list/)

编写一个函数，接受按非递减顺序排序的列表，并从列表中删除任何重复的节点。该列表只能遍历一次。
例如，如果链接列表是 11->11->11->21->43->43->60，则 removeDuplicates()应该将列表转换为 11- > 21- > 43- > 60。

**算法:**
从头(或开始)节点遍历列表。遍历时，将每个节点与其下一个节点进行比较。如果下一个节点的数据与当前节点相同，则删除下一个节点。在删除节点之前，我们需要存储节点的下一个指针

**实现:**
removeDuplicates()之外的函数只是创建一个链表并测试 remove duplicates()。

## C++

```cpp
// C++ Program to remove duplicates 
// from a sorted linked list 
#include <bits/stdc++.h>
using namespace std;

// Link list node 
class Node 
{ 
    public:
    int data; 
    Node* next; 
}; 

// The function removes duplicates 
// from a sorted list 
void removeDuplicates(Node* head) 
{ 
    // Pointer to traverse the linked list 
    Node* current = head; 

    // Pointer to store the next pointer 
    // of a node to be deleted
    Node* next_next; 

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

        // This is tricky: only advance if no deletion 
        else 
        { 
            current = current->next; 
        } 
    } 
} 

// UTILITY FUNCTIONS 
// Function to insert a node at the 
// beginning of the linked list 
void push(Node** head_ref, int new_data) 
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

// Function to print nodes in a 
// given linked list 
void printList(Node *node) 
{ 
    while (node != NULL) 
    { 
        cout << " " << node->data; 
        node = node->next; 
    } 
} 

// Driver code
int main() 
{ 
    // Start with the empty list 
    Node* head = NULL; 

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

    cout << "Linked list before duplicate removal "; 
    printList(head); 

    // Remove duplicates from linked list 
    removeDuplicates(head); 

    cout << "Linked list after duplicate removal ";     
    printList(head);             

    return 0; 
} 
// This code is contributed by rathbhupendra
```

**输出:**

```cpp
Linked list before duplicate removal  11 11 11 13 13 20
Linked list after duplicate removal  11 13 20
```

**时间复杂度:** O(n)，其中 n 是给定链表中的节点数。

**递归方法:**

## C++

```cpp
// C++ Program to remove duplicates
// from a sorted linked list 
#include <bits/stdc++.h>
using namespace std;

// Link list node 
class Node 
{ 
    public:
    int data; 
    Node* next; 
}; 

// The function removes duplicates 
// from a sorted list 
void removeDuplicates(Node* head) 
{ 
    // Pointer to store the pointer 
    // of a node to be deleted*/
    Node* to_free; 

    // Do nothing if the list is empty 
    if (head == NULL) 
        return; 

    // Traverse the list till last node 
    if (head->next != NULL) 
    {         
        // Compare head node with next node 
        if (head->data == head->next->data) 
        { 
            /* The sequence of steps is important.
               to_free pointer stores the next of 
               head pointer which is to be deleted.*/    
            to_free = head->next; 
            head->next = head->next->next;
            free(to_free);
            removeDuplicates(head);
        } 

        /* This is tricky: only advance if 
           no deletion */

        else         
        { 
            removeDuplicates(head->next);
        } 
    } 
} 

// UTILITY FUNCTIONS 
// Function to insert a node at the
// beginning of the linked list 
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

/* Function to print nodes 
   in a given linked list */
void printList(Node *node) 
{ 
    while (node != NULL) 
    { 
        cout << " " << node->data; 
        node = node->next; 
    } 
} 

// Driver code
int main() 
{ 
    // Start with the empty list 
    Node* head = NULL; 

    /* Let us create a sorted linked
       list to test the functions 
       Created linked list will be 
       11->11->11->13->13->20 */
    push(&head, 20); 
    push(&head, 13); 
    push(&head, 13); 
    push(&head, 11); 
    push(&head, 11); 
    push(&head, 11);                                     

    cout << 
    "Linked list before duplicate removal "; 
    printList(head); 

    // Remove duplicates from linked list 
    removeDuplicates(head); 

    cout << 
    "Linked list after duplicate removal ";     
    printList(head);             

    return 0; 
} 
// This code is contributed by Ashita Gupta
```

**输出:**

```cpp
Linked list before duplicate removal  11 11 11 13 13 20
Linked list after duplicate removal  11 13 20
```

**另一种方法:**创建一个指向每个元素第一次出现的指针和另一个将迭代到每个元素的指针 temp，当前一个指针的值不等于 temp 指针时，我们将前一个指针的指针设置为另一个节点的第一次出现。

下面是上述方法的实现:

## C++

```cpp
// C++ program to remove duplicates
// from a sorted linked list
#include <bits/stdc++.h>
using namespace std;

// Linked list Node
struct Node
{
    int data;
    Node *next;
    Node(int d)
    {
      data = d;
      next = NULL;
    }
};

// Function to remove duplicates
// from the given linked list
Node *removeDuplicates(Node *head)
{  
    // Two references to head temp will 
    // iterate to the whole Linked List
    // prev will point towards the first 
    // occurrence of every element
    Node *temp = head,*prev=head;

    // Traverse list till the last node
    while (temp != NULL) 
    {
       // Compare values of both pointers
       if(temp->data != prev->data)
       {         
           /* if the value of prev is not equal 
              to the value of temp that means 
              there are no more occurrences of 
              the prev data-> So we can set the 
              next of prev to the temp node->*/
           prev->next = temp;
           prev = temp;
       }

        // Set the temp to the next node
        temp = temp->next;
    }

    /* This is the edge case if there are more than 
       one occurrences of the last element */
    if(prev != temp)
    {
        prev->next = NULL;
    }
    return head;
}

Node *push(Node *head, int new_data)
{  
    /* 1 & 2: Allocate the Node &
              Put in the data*/
    Node *new_node = new Node(new_data);

    /* 3\. Make next of new Node as head */
          new_node->next = head;

    /* 4\. Move the head to point to new Node */
    head = new_node;
    return head;
}

// Function to print linked list 
void printList(Node *head)
{
    Node *temp = head;
    while (temp != NULL)
    {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}

// Driver code 
int main()
{
    Node *llist = NULL;
    llist = push(llist,20);
    llist = push(llist,13);
    llist = push(llist,13);
    llist = push(llist,11);
    llist = push(llist,11);
    llist = push(llist,11);
    cout << 
    ("List before removal of duplicates");
    printList(llist);
    cout << 
    ("List after removal of elements");
    llist = removeDuplicates(llist);
    printList(llist);
}
// This code is contributed by mohit kumar 29.
```

**输出:**

```cpp
List before removal of duplicates
11 11 11 13 13 20 
List after removal of elements
11 13 20 
```

**另一种方法:使用地图**

这个想法是推送地图中的所有值并打印其关键点。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Link list node 
struct Node 
{
    int data;
    Node* next;
    Node()
    {
        data = 0;
        next = NULL;
    }
};

/* Function to insert a node at 
   the beginning of the linked
   list */
void push(Node** head_ref, 
          int new_data)
{    
    // Allocate node 
    Node* new_node = new Node();

    // Put in the data 
    new_node->data = new_data;

    // Link the old list off 
    // the new node 
    new_node->next = (*head_ref);

    // Move the head to point
    // to the new node 
    (*head_ref) = new_node;
}

/* Function to print nodes 
   in a given linked list */
void printList(Node* node)
{
    while (node != NULL) 
    {
        cout << node->data << " ";
        node = node->next;
    }
}

// Function to remove duplicates
void removeDuplicates(Node* head)
{
    unordered_map<int, bool> track;
    Node* temp = head;
    while (temp) 
    {
        if (track.find(temp->data) == track.end()) 
        {
            cout << temp->data << " ";
        }
        track[temp->data] = true;
        temp = temp->next;
    }
}

// Driver Code
int main()
{
    Node* head = NULL;

    /* Created linked list will be
       11->11->11->13->13->20 */
    push(&head, 20);
    push(&head, 13);
    push(&head, 13);
    push(&head, 11);
    push(&head, 11);
    push(&head, 11);

    cout << 
    "Linked list before duplicate removal ";
    printList(head);

    cout << 
    "Linked list after duplicate removal ";
    removeDuplicates(head);

    return 0;
}
// This code is contributed by yashbeersingh42
```

**输出:**

```cpp
Linked list before duplicate removal 11 11 11 13 13 20 
Linked list after duplicate removal 11 13 20 
```

**时间复杂度:** O(节点数)

**空间复杂度:** O(节点数)

更多详情请参考[从排序链表](https://www.geeksforgeeks.org/remove-duplicates-from-a-sorted-linked-list/)中删除重复项的完整文章！