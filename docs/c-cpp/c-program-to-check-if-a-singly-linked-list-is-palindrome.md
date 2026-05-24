# 检查单链表是否回文的 C 程序

> 原文:[https://www . geesforgeks . org/c-program-to-check-if-a-single-link-list-is-回文/](https://www.geeksforgeeks.org/c-program-to-check-if-a-singly-linked-list-is-palindrome/)

给定一个字符的单链表，写一个函数，如果给定的列表是回文，则返回 true，否则返回 false。

![Palindrome Linked List](img/7eef7faffebfb5a692784722f81c0a42.png)

**方法 1(通过反转列表):**
这个方法需要 O(n)个时间和 O(1)个额外空间。
**1)** 获得链表的中间。
**2)** 反转后半部分链表。
**3)** 检查前半部分和后半部分是否相同。
**4)** 通过再次反转后半部分并将其附着回前半部分来构建原始链表

将列表分成两半，使用[这个](https://www.geeksforgeeks.org/write-a-c-function-to-print-the-middle-of-the-linked-list/)帖子的方法 2。

当节点数为偶数时，第一半和第二半正好包含一半节点。这种方法的挑战是处理节点数为奇数的情况。我们不希望中间节点成为列表的一部分，因为我们要比较它们是否相等。对于奇数情况，我们使用一个单独的变量“中间节点”。

## C

```cpp
// C++ program to check if a linked list
// is palindrome
#include <stdbool.h>
#include <stdio.h>
#include <stdlib.h>

// Link list node
struct Node
{
    char data;
    struct Node* next;
};

void reverse(struct Node**);
bool compareLists(struct Node*,
                  struct Node*);

// Function to check if given linked
// list is palindrome or not
bool isPalindrome(struct Node* head)
{
    struct Node *slow_ptr = head,
                *fast_ptr = head;
    struct Node *second_half,
                *prev_of_slow_ptr = head;

    // To handle odd size list 
    struct Node* midnode = NULL;

    // Initialize result
    bool res = true;

    if (head != NULL &&
        head->next != NULL)
    {
        // Get the middle of the list.
        // Move slow_ptr by 1 and
        // fast_ptrr by 2, slow_ptr
        // will have the middle node
        while (fast_ptr != NULL &&
               fast_ptr->next != NULL)
        {
            fast_ptr = fast_ptr->next->next;

            // We need previous of the slow_ptr for
            // linked lists with odd elements
            prev_of_slow_ptr = slow_ptr;
            slow_ptr = slow_ptr->next;
        }

        /* fast_ptr would become NULL when there
           are even elements in list. And not NULL
           for odd elements. We need to skip the
           middle node for odd case and store it
           somewhere so that we can restore the
           original list*/
        if (fast_ptr != NULL)
        {
            midnode = slow_ptr;
            slow_ptr = slow_ptr->next;
        }

        // Now reverse the second half and
        // compare it with first half
        second_half = slow_ptr;

        // NULL terminate first half
        prev_of_slow_ptr->next = NULL;

        // Reverse the second half
        reverse(&second_half);

        // Compare
        res = compareLists(head, second_half);

        // Construct the original list back
        // Reverse the second half again
        reverse(&second_half);

        // If there was a mid node (odd size
        // case) which was not part of either
        // first half or second half.
        if (midnode != NULL)
        {
            prev_of_slow_ptr->next = midnode;
            midnode->next = second_half;
        }
        else
            prev_of_slow_ptr->next = second_half;
    }
    return res;
}

// Function to reverse the linked list
// Note that this function may change
// the head
void reverse(struct Node** head_ref)
{
    struct Node* prev = NULL;
    struct Node* current = *head_ref;
    struct Node* next;
    while (current != NULL)
    {
        next = current->next;
        current->next = prev;
        prev = current;
        current = next;
    }
    *head_ref = prev;
}

// Function to check if two input
// lists have same data
bool compareLists(struct Node* head1,
                  struct Node* head2)
{
    struct Node* temp1 = head1;
    struct Node* temp2 = head2;

    while (temp1 && temp2)
    {
        if (temp1->data == temp2->data)
        {
            temp1 = temp1->next;
            temp2 = temp2->next;
        }
        else
            return 0;
    }

    // Both are empty return 1
    if (temp1 == NULL && temp2 == NULL)
        return 1;

    // Will reach here when one is NULL
    // and other is not
    return 0;
}

// Push a node to linked list.
// Note that this function
// changes the head
void push(struct Node** head_ref,
          char new_data)
{
    // allocate node
    struct Node* new_node =
           (struct Node*)malloc(sizeof(struct Node));

    // Put in the data
    new_node->data = new_data;

    // Link the old list off the new node
    new_node->next = (*head_ref);

    // Move the head to pochar to the new node
    (*head_ref) = new_node;
}

// A utility function to print a
// given linked list
void printList(struct Node* ptr)
{
    while (ptr != NULL)
    {
        printf("%c->", ptr->data);
        ptr = ptr->next;
    }
    printf("NULL");
}

// Driver code
int main()
{
    // Start with the empty list
    struct Node* head = NULL;
    char str[] = "abacaba";
    int i;

    for (i = 0; str[i] != ''; i++)
    {
        push(&head, str[i]);
        printList(head);
        isPalindrome(head) ? printf("Is Palindrome") : printf("Not Palindrome");
    }
    return 0;
}
```

**输出:**

```cpp
a->NULL
Is Palindrome

b->a->NULL
Not Palindrome

a->b->a->NULL
Is Palindrome

c->a->b->a->NULL
Not Palindrome

a->c->a->b->a->NULL
Not Palindrome

b->a->c->a->b->a->NULL
Not Palindrome

a->b->a->c->a->b->a->NULL
Is Palindrome
```

**时间复杂度:**O(n)
T3】辅助空间: O(1)

**方法 2(使用递归):**
使用左右两个指针。使用递归左右移动，并检查每个递归调用中的后续操作。
1)子列表是回文。
2)当前左右值匹配。

如果以上两个条件都成立，那么返回真。

其思想是使用函数调用堆栈作为容器。递归遍历，直到列表结束。当我们从最后一个空值返回时，我们将处于最后一个节点。最后一个节点将与列表的第一个节点进行比较。

为了访问列表的第一个节点，我们需要列表头在递归的最后一次调用中可用。因此，我们也将 head 传递给递归函数。如果它们都匹配，我们需要比较(2，n-2)个节点。同样，当递归回落到(n-2)第二个节点时，我们需要从头部引用第二个节点。我们在前面的调用中推进头指针，以引用列表中的下一个节点。
然而，诀窍在于识别双指针。传递一个指针就像传递一个值一样好，我们会一次又一次地传递同一个指针。我们需要传递头指针的地址，以反映父递归调用的变化。
感谢**沙拉德·钱德拉**提出这个方法。

## C

```cpp
// Recursive program to check if a
// given linked list is palindrome
#include <stdbool.h>
#include <stdio.h>
#include <stdlib.h>

// Link list node
struct node
{
    char data;
    struct node* next;
};

// Initial parameters to this
// function are &head and head
bool isPalindromeUtil(struct node** left,
                      struct node* right)
{
    // Stop recursion when right
    // becomes NULL
    if (right == NULL)
        return true;

    // If sub-list is not palindrome then
    // no need to check for current left
    // and right, return false
    bool isp = isPalindromeUtil(left,
                                right->next);
    if (isp == false)
        return false;

    // Check values at current left and right
    bool isp1 = (right->data == (*left)->data);

    // Move left to next node
    *left = (*left)->next;

    return isp1;
}

// A wrapper over isPalindromeUtil()
bool isPalindrome(struct node* head)
{
    isPalindromeUtil(&head, head);
}

// Push a node to linked list.
// Note that this function changes
// the head
void push(struct node** head_ref,
          char new_data)
{
    // Allocate node
    struct node* new_node =
          (struct node*)malloc(sizeof(struct node));

    // Put in the data
    new_node->data = new_data;

    // Link the old list off the new node
    new_node->next = (*head_ref);

    // Move the head to pochar to the new node
    (*head_ref) = new_node;
}

// A utility function to print a
// given linked list
void printList(struct node* ptr)
{
    while (ptr != NULL)
    {
        printf("%c->", ptr->data);
        ptr = ptr->next;
    }
    printf("NULL\n");
}

// Driver code
int main()
{
    // Start with the empty list
    struct node* head = NULL;
    char str[] = "abacaba";
    int i;

    for (i = 0; str[i] != '\0'; i++)
    {
        push(&head, str[i]);
        printList(head);
        isPalindrome(head) ? printf("Is Palindrome\n\n") : printf("Not Palindrome\n\n");
    }

    return 0;
}
```

**输出:**

```cpp
a->NULL
Not Palindrome

b->a->NULL
Not Palindrome

a->b->a->NULL
Is Palindrome

c->a->b->a->NULL
Not Palindrome

a->c->a->b->a->NULL
Not Palindrome

b->a->c->a->b->a->NULL
Not Palindrome

a->b->a->c->a->b->a->NULL
Is Palindrome
```

**时间复杂度:**O(n)
T3】辅助空间: O(n)如果考虑函数调用栈大小，否则为 O(1)。

更多详情请参考[函数整篇文章，查看单链表是否回文](https://www.geeksforgeeks.org/function-to-check-if-a-singly-linked-list-is-palindrome/)！