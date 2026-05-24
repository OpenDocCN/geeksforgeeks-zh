# C++ 中的指针引用：示例与应用

> 原文：[https://www.geeksforgeeks.org/reference-to-a-pointer-in-c-with-examples-and-applications/](https://www.geeksforgeeks.org/reference-to-a-pointer-in-c-with-examples-and-applications/)

## 概念介绍

就像引用简单数据类型一样，我们也可以引用指针。

```cpp
// CPP program to demonstrate references to pointers.
#include <iostream>
using namespace std;

int main()
{
    int x = 10;

    // ptr1 holds address of x
    int* ptr1 = &x;

    // Now ptr2 also holds address of x.
    // But note that pt2 is an alias of ptr1.
    // So if we change any of these two to
    // hold some other address, the other
    // pointer will also change.
    int*& ptr2 = ptr1;

    int y = 20;
    ptr2 = &y;

    // Below line prints 20, 20, 10, 20
    // Note that ptr1 also starts pointing
    // to y.
    cout << *ptr1 << " " << *ptr2 << " "
         << x << " " << y;

    return 0;
}
```

`Output:`

```cpp
20 20 10 20
```

## 应用场景

考虑这样一种情况，我们传递一个指向函数的指针，并且希望函数能够修改该指针使其指向其他东西，同时我们希望这些变化能够反映在调用者身上。例如，编写一个改变链表头部的函数，我们可以将指针的引用传递给头部，这样函数就可以改变头部（另一种方法是返回新的头部）。我们也可以使用双指针实现同样的事情。

```cpp
// A C++ program to demonstrate application
// of reference to a pointer.
#include <iostream>
using namespace std;

// A linked list node
struct Node {
    int data;
    struct Node* next;
};

/* Given a reference to pointer to the head of
   a list, insert a new value x at head */
void push(struct Node *&head, int x)
{
    struct Node* new_node = new Node;
    new_node->data = x;
    new_node->next = head;
    head = new_node;
}

// This function prints contents of linked
// list starting from head
void printList(struct Node* node)
{
    while (node != NULL) {
        cout << node->data << " ";
        node = node->next;
    }
}

/* Driver program to test above functions*/
int main()
{
    /* Start with the empty list */
    struct Node* head = NULL;
    push(head, 1);
    push(head, 2);
    push(head, 3);

    printList(head);

    return 0;
}
```

`Output:`

```cpp
3 2 1
```