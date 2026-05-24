# 用于从未排序的链表中删除重复项的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-从未排序的链接列表中删除重复项的程序/](https://www.geeksforgeeks.org/cpp-program-for-removing-duplicates-from-an-unsorted-linked-list/)

编写一个 removeDuplicates()函数，该函数获取一个列表并从列表中删除任何重复的节点。列表未排序。
例如，如果链接列表是 12->11->12->21->41->43->21，则 removeDuplicates()应该将列表转换为 12->11->21->41->43。

**方法 1(使用两个循环):**
这是使用两个循环的简单方法。外环用于逐个拾取元素，内环将拾取的元素与其余元素进行比较。
感谢 Gaurav Saxena 对编写这段代码的帮助。

## C++

```cpp
// C++ Program to remove duplicates in an 
// unsorted linked list 
#include <bits/stdc++.h>
using namespace std;

// A linked list node 
struct Node 
{
    int data;
    struct Node* next;
};

// Utility function to create a 
// new Node
struct Node* newNode(int data)
{
    Node* temp = new Node;
    temp->data = data;
    temp->next = NULL;
    return temp;
}

/* Function to remove duplicates from a
   unsorted linked list */
void removeDuplicates(struct Node* start)
{
    struct Node *ptr1, *ptr2, *dup;
    ptr1 = start;

    // Pick elements one by one 
    while (ptr1 != NULL &&
           ptr1->next != NULL) 
    {
        ptr2 = ptr1;

        /* Compare the picked element with rest
           of the elements */
        while (ptr2->next != NULL) 
        {
            /* If duplicate then delete it */
            if (ptr1->data == ptr2->next->data) 
            {
                // Sequence of steps is important here 
                dup = ptr2->next;
                ptr2->next = ptr2->next->next;
                delete (dup);
            }
            else 
                ptr2 = ptr2->next;
        }
        ptr1 = ptr1->next;
    }
}

// Function to print nodes in a given 
// linked list 
void printList(struct Node* node)
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
    // The constructed linked list is:
    // 10->12->11->11->12->11->10
    struct Node* start = newNode(10);
    start->next = newNode(12);
    start->next->next = newNode(11);
    start->next->next->next = newNode(11);
    start->next->next->next->next = newNode(12);
    start->next->next->next->next->next = newNode(11);
    start->next->next->next->next->next->next = newNode(10);

    printf("Linked list before removing duplicates ");
    printList(start);
    removeDuplicates(start);

    printf("Linked list after removing duplicates ");
    printList(start);
    return 0;
}
```

**输出:**

```cpp
Linked list before removing duplicates:
10 12 11 11 12 11 10 
Linked list after removing duplicates:
10 12 11
```

**时间复杂度:** O(n^2)

**方法 2(使用排序):**
一般来说，合并排序是最适合高效排序链表的排序算法。
1)使用合并排序对元素进行排序。我们很快会写一篇关于排序链表的文章。O(nLogn)
2)使用[算法在线性时间内移除重复项，以移除排序链表中的重复项。O(n)](https://www.geeksforgeeks.org/remove-duplicates-from-a-sorted-linked-list/)
请注意，这种方法没有保留元素的原始顺序。
**时间复杂度:** O(nLogn)

**方法 3(使用哈希):**
我们从头到尾遍历链接列表。对于每一个新遇到的元素，我们检查它是否在哈希表中:如果是，我们删除它；否则我们把它放到散列表中。

## C++

```cpp
// C++ Program to remove duplicates in an 
// unsorted linked list
#include<bits/stdc++.h>
using namespace std;

// A linked list node 
struct Node
{
    int data;
    struct Node *next;
};

// Utility function to create a 
// new Node
struct Node *newNode(int data)
{
   Node *temp = new Node;
   temp->data = data;
   temp->next = NULL;
   return temp;
}

/* Function to remove duplicates from a
   unsorted linked list */
void removeDuplicates(struct Node *start)
{
    // Hash to store seen values
    unordered_set<int> seen;

    // Pick elements one by one 
    struct Node *curr = start;
    struct Node *prev = NULL;
    while (curr != NULL)
    {
        // If current value is seen before
        if (seen.find(curr->data) != seen.end())
        {
           prev->next = curr->next;
           delete (curr);
        }
        else
        {
           seen.insert(curr->data);
           prev = curr;
        }
        curr = prev->next;
    }
}

// Function to print nodes in a given 
// linked list 
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
    /* The constructed linked list is:
       10->12->11->11->12->11->10*/
    struct Node *start = newNode(10);
    start->next = newNode(12);
    start->next->next = newNode(11);
    start->next->next->next = newNode(11);
    start->next->next->next->next = newNode(12);
    start->next->next->next->next->next = newNode(11);
    start->next->next->next->next->next->next = newNode(10);

    printf("Linked list before removing duplicates : ");
    printList(start);
    removeDuplicates(start);

    printf("Linked list after removing duplicates : ");
    printList(start);
    return 0;
}
```

**输出:**

```cpp
Linked list before removing duplicates:
10 12 11 11 12 11 10 
Linked list after removing duplicates:
10 12 11
```

感谢 bearwang 提出这个方法。
**时间复杂度:**平均 O(n)(假设哈希表访问时间平均为 O(1))。

更多详细信息，请参考完整文章[从未排序的链表](https://www.geeksforgeeks.org/remove-duplicates-from-an-unsorted-linked-list/)中删除重复项！