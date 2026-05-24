# 链表类

中的运算符重载“< >”

> 原文:[https://www . geesforgeks . org/operator-overload-and-operator-in-a-link-list-class/](https://www.geeksforgeeks.org/operator-overloading-and-operator-in-a-linked-list-class/)

**先决条件:**[c++ 中的运算符重载](https://www.geeksforgeeks.org/operator-overloading-c/)[c++ 中的链表](https://www.geeksforgeeks.org/linked-list-set-1-introduction/)

C++ 自带的库提供了执行[输入和输出](https://www.geeksforgeeks.org/basic-input-output-c/)的方法。在 C++ 中，输入和输出作为字节序列执行，也称为流。[输入和输出流](https://www.geeksforgeeks.org/basic-input-output-c/)由 iostream 库管理。 **cin** 和 **cout** 是输入流和输出流的标准对象。

我们可以重载**'>>'****'<<'**操作符，在[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)中进行输入，在 C++ 中打印[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)中的元素。它能够为操作符提供一种特殊的数据类型含义，这种能力被称为[操作符重载](https://www.geeksforgeeks.org/operator-overloading-c/)。

重载运算符的语法如下:

```cpp
returnType operator symbol (arguments)
{
   Operations...
} 
```

**<u>【伊斯特朗操作员】>></u>**

## C++

```cpp
istream& operator>>(istream& is, node*& head)
{
    // Function call to overload the ">>"
    // operator
    takeInput(head);
}
```

**解释:**
上述函数的返回类型是对 istream 对象的引用。声明中“ **cin > >头像；**，cin 是第一个参数，对头部的引用是函数的第二个参数。执行任何此类语句时，都会调用上述函数。

**<u>【超载牡蛎操作员】<<:</u>**

## C++

```cpp
ostream& operator<<(ostream& os, node* head)
{
    // Function call to overload the "<<"
    // operator
    print(head);
}
```

**说明:**
上述函数的返回类型是对 ostream 对象的引用。在声明“ **cout < <头；**”，cout 是第一个参数，对 head 的引用是函数的第二个参数。执行任何此类语句时，都会调用上述函数。

**<u><>超载代码【操作员:</u>**

下面是**'>>'****'<<'**运算符重载的代码，连续以一个数字 **N** 作为输入，在链表中插入数字 **N** ，直到 **N** = -1。

## C++

```cpp
// C++ program to demonstrate the
// overloading of '<<' and '>>'
// operators
#include <iostream>
using namespace std;

// Class for each node object
// of the linked list
class node {
public:
    // Node of the linked list
    int data;
    node* next;

    // Constructor of node class
    node(int d)
    {
        data = d;
        next = NULL;
    }
};

// Insert a node at head of linked
// list
void insertAtHead(node*& head, int d)
{
    node* n = new node(d);
    n->next = head;
    head = n;
}

// Insert a node at tail of linked
// list
void insertAtTail(node* head, int data)
{
    // Make new node using
    // constructor
    node* n = new node(data);
    node* temp = head;

    // Traverse till we get to end of
    // the linked list
    while (temp->next != NULL)
        temp = temp->next;

    // Append the new node n at the end
    // of the linked list
    temp->next = n;
}

// Print the node at the linked list
void print(node* head)
{
    // Print the first Node
    if (head != NULL) {
        cout << head->data;
        head = head->next;
    }

    // Traverse till head traverse
    // till end
    while (head != NULL) {
        cout << "->" << head->data;
        head = head->next;
    }
}

// Function that takes continuous input
// until user enter -1 while initializing
// the linked list.
void takeInput(node*& head)
{
    int n;
    cin >> n;

    // If n is not equals to -1 insert
    // the node in the linked list
    while (n != -1) {

        // If head is NULL, insert at
        // the beginning of list
        if (head == NULL)
            insertAtHead(head, n);
        else
            insertAtTail(head, n);
        cin >> n;
    }
}

// Overloading the ostream operator '<<'
// to print the complete linked list from
// beginning
ostream& operator<<(ostream& os, node* head)
{
    print(head);
}

// Overloading the istream operator '>>'
// to take continuous input into the linked
// list until user inputs -1
istream& operator>>(istream& is, node*& head)
{
    takeInput(head);
}

// Driver Code
int main()
{
    // initialise head to NULL
    node* head = NULL;

    // Overloading of '>>' for inserting
    // element in the linked list
    cin >> head;

    // Overloading of '<<' for printing
    // element in the linked list
    cout << head;
    return 0;
}
```