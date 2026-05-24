# C# 程序打印链表的反转而不实际反转

> 原文:[https://www . geesforgeks . org/c-打印程序-链表的反向而不实际反向-2/](https://www.geeksforgeeks.org/c-program-for-printing-reverse-of-a-linked-list-without-actually-reversing-2/)

给定一个链表，使用递归函数打印它的逆序。例如，如果给定的链表是 1->2->3->4，那么输出应该是 4->3->2->1。
注意，问题只是关于打印反面。要反转列表本身请参见[本](https://www.geeksforgeeks.org/reverse-a-linked-list/)T3**难度等级:**菜鸟

![reverse-a-link-list](img/2887a61ccc887b8c68af722f22f72ab8.png)

**算法:**

```cs
printReverse(head)
  1\. call print reverse for head->next
  2\. print head->data
```

**实施:**

## C#

```cs
// C# program to print reverse 
// of a linked list
using System;

public class LinkedList
{
    // Head of list
    Node head; 

    // Linked list Node
    class Node
    {
        public int data;
        public Node next;
        public Node(int d) 
        {
            data = d; next = null;
        }
    }

    // Function to print reverse 
    // of linked list 
    void printReverse(Node head)
    {
        if (head == null) return;

        // print list of head node
        printReverse(head.next);

        // After everything else is printed
        Console.Write(head.data + " ");
    }

    // Utility Functions 

    // Inserts a new Node at front 
    // of the list. 
    public void push(int new_data)
    {
        /* 1 & 2: Allocate the Node &
                  Put in the data*/
        Node new_node = new Node(new_data);

        // 3\. Make next of new Node as head 
        new_node.next = head;

        // 4\. Move the head to point to 
        // new Node 
        head = new_node;
    }

    // Driver code
    public static void Main(String []args)
    {
        // Let us create linked list 1->2->3->4
        LinkedList llist = new LinkedList();
        llist.push(4);
        llist.push(3);
        llist.push(2);
        llist.push(1);

        llist.printReverse(llist.head);
    }
}
// This code is contributed by Rajput-Ji 
```

**输出:**

```cs
4 3 2 1
```

**时间复杂度:** O(n)

更多详情请参考[打印链表的反转而不实际反转](https://www.geeksforgeeks.org/print-reverse-of-a-linked-list-without-actually-reversing/)的完整文章！