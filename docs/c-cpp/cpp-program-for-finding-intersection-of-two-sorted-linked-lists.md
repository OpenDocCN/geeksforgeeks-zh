# 寻找两个排序链表交集的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-寻找两个排序链表交集的程序/](https://www.geeksforgeeks.org/cpp-program-for-finding-intersection-of-two-sorted-linked-lists/)

给定两个按递增顺序排序的列表，创建并返回一个表示这两个列表交集的新列表。新的列表应该有自己的记忆——原来的列表不应该改变。

**示例:**

```cpp
Input: 
First linked list: 1->2->3->4->6
Second linked list be 2->4->6->8, 
Output: 2->4->6.
The elements 2, 4, 6 are common in 
both the list so they appear in the 
intersection list. 

Input: 
First linked list: 1->2->3->4->5
Second linked list be 2->3->4, 
Output: 2->3->4
The elements 2, 3, 4 are common in 
both the list so they appear in the 
intersection list.
```

**<u>方法 1</u> :** 使用虚拟节点。
**方法:**
想法是在结果列表的开头使用一个临时伪节点。指针尾部总是指向结果列表中的最后一个节点，因此可以轻松添加新节点。伪节点最初给尾部一个内存空间来指向。这个虚拟节点是有效的，因为它只是临时的，并且是在堆栈中分配的。循环继续，从“a”或“b”中删除一个节点，并将其添加到尾部。当遍历给定的列表时，结果是伪的。接下来，当从虚拟的下一个节点分配值时。如果两个元素相等，则移除两个元素并将元素插入尾部。否则删除两个列表中较小的元素。

下面是上述方法的实现:

## C++

```cpp
#include<bits/stdc++.h>
using namespace std;

// Link list node 
struct Node 
{
    int data;
    Node* next;
};

void push(Node** head_ref, 
          int new_data);

/* This solution uses the temporary
  dummy to build up the result list */
Node* sortedIntersect(Node* a, Node* b)
{
    Node dummy;
    Node* tail = &dummy;
    dummy.next = NULL;

    /* Once one or the other 
       list runs out -- we're done */
    while (a != NULL && b != NULL) 
    {
        if (a->data == b->data) 
        {
            push((&tail->next), a->data);
            tail = tail->next;
            a = a->next;
            b = b->next;
        }
        // Advance the smaller list 
        else if (a->data < b->data)
            a = a->next;
        else
            b = b->next;
    }
    return (dummy.next);
}

// UTILITY FUNCTIONS 
/* Function to insert a node at 
   the beginning of the linked list */
void push(Node** head_ref, int new_data)
{
    // Allocate node 
    Node* new_node = 
          (Node*)malloc(sizeof(Node));

    // Put in the data  
    new_node->data = new_data;

    // Link the old list off the 
    // new node 
    new_node->next = (*head_ref);

    // Move the head to point to 
    // the new node 
    (*head_ref) = new_node;
}

/* Function to print nodes in 
   a given linked list */
void printList(Node* node)
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
    // Start with the empty lists 
    Node* a = NULL;
    Node* b = NULL;
    Node* intersect = NULL;

    /* Let us create the first sorted 
       linked list to test the functions
       Created linked list will be 
       1->2->3->4->5->6 */
    push(&a, 6);
    push(&a, 5);
    push(&a, 4);
    push(&a, 3);
    push(&a, 2);
    push(&a, 1);

    /* Let us create the second sorted 
       linked list. Created linked list 
       will be 2->4->6->8 */
    push(&b, 8);
    push(&b, 6);
    push(&b, 4);
    push(&b, 2);

    // Find the intersection two linked lists 
    intersect = sortedIntersect(a, b);

    cout << 
    "Linked list containing common items of a & b ";
    printList(intersect);
}
```

**输出:**

```cpp
Linked list containing common items of a & b 
2 4 6 
```

**复杂度分析:**

*   **时间复杂度:** O(m+n)，其中 m 和 n 分别是第一和第二链表中的节点数。
    只需要遍历列表一次。
*   **辅助空间:** O(min(m，n))。
    输出列表最多可以存储(m，n)个节点。

**<u>方法二</u> :** 递归求解。
**方法:**
递归方法与上述两种方法非常相似。构建一个递归函数，该函数接受两个节点并返回一个链表节点。比较两个列表的第一个元素。

*   如果它们相似，那么用两个列表的下一个节点调用递归函数。用当前节点的数据创建一个节点，并将递归函数返回的节点放在所创建节点的下一个指针上。返回创建的节点。
*   如果值不相等，则移除两个列表中较小的节点，并调用递归函数。

下面是上述方法的实现:

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Link list node 
struct Node 
{
    int data;
    struct Node* next;
};

struct Node* sortedIntersect(struct Node* a,
                             struct Node* b)
{    
    // Base case 
    if (a == NULL || b == NULL)
        return NULL;

    // If both lists are non-empty 

    /* Advance the smaller list and
       call recursively */
    if (a->data < b->data)
        return sortedIntersect(a->next, b);

    if (a->data > b->data)
        return sortedIntersect(a, b->next);

    // Below lines are executed only
    // when a->data == b->data
    struct Node* temp = 
           (struct Node*)malloc(sizeof(struct Node));
    temp->data = a->data;

    // Advance both lists and call recursively
    temp->next = sortedIntersect(a->next, 
                                 b->next);
    return temp;
}

// UTILITY FUNCTIONS 
/* Function to insert a node at 
   the beginning of the linked list */
void push(struct Node** head_ref, 
          int new_data)
{    
    // Allocate node 
    struct Node* new_node = 
           (struct Node*)malloc(sizeof(struct Node));

    // Put in the data  
    new_node->data = new_data;

    // Link the old list off the 
    // new node 
    new_node->next = (*head_ref);

    // Move the head to point to 
    // the new node 
    (*head_ref) = new_node;
}

/* Function to print nodes in
   a given linked list */
void printList(struct Node* node)
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
    // Start with the empty lists 
    struct Node* a = NULL;
    struct Node* b = NULL;
    struct Node* intersect = NULL;

    /* Let us create the first sorted
       linked list to test the functions
       Created linked list will be 
       1->2->3->4->5->6 */
    push(&a, 6);
    push(&a, 5);
    push(&a, 4);
    push(&a, 3);
    push(&a, 2);
    push(&a, 1);

    /* Let us create the second sorted 
       linked list. Created linked list 
       will be 2->4->6->8 */
    push(&b, 8);
    push(&b, 6);
    push(&b, 4);
    push(&b, 2);

    // Find the intersection two linked lists 
    intersect = sortedIntersect(a, b);

    cout << "Linked list containing " << 
            "common items of a & b ";
    printList(intersect);

    return 0;
}
// This code is contributed by shivanisinghss2110
```

**输出:**

```cpp
Linked list containing common items of a & b 
2 4 6
```

**复杂度分析:**

*   **时间复杂度:** O(m+n)，其中 m 和 n 分别是第一和第二链表中的节点数。
    只需要遍历列表一次。
*   **辅助空间:** O(最大(m，n))。
    输出列表最多可以存储 m+n 个节点。

更多详情请参考完整文章[两个排序链表的交集](https://www.geeksforgeeks.org/intersection-of-two-sorted-linked-lists/)！