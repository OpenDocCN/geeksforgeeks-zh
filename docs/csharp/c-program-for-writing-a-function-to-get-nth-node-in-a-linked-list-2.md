# 用于编写函数以获取链表中第 n 个节点的 C# 程序

> 原文:[https://www . geesforgeks . org/c-写程序-函数-获取链表中的第 n 个节点-2/](https://www.geeksforgeeks.org/c-program-for-writing-a-function-to-get-nth-node-in-a-linked-list-2/)

编写一个 GetNth()函数，该函数接受一个链表和一个整数索引，并返回存储在该索引位置的节点中的数据值。

**例:**

```cs
Input:  1->10->30->14,  index = 2
Output: 30  
The node at index 2 is 30
```

**算法:**

```cs
1\. Initialize count = 0
2\. Loop through the link list
     a. If count is equal to the passed index then return current
         node
     b. Increment count
     c. Change current to point to next of the current.
```

**实施:**

## C#

```cs
// C# program to find n'th node 
// in linked list
using System;
using System.Diagnostics;

public class Node 
{
    public int data;
    public Node next;
    public Node(int d)
    {
        data = d;
        next = null;
    }
}

class LinkedList 
{
    // Head of list
    Node head; 

    // Takes index as argument and 
    // return data at index
    public int GetNth(int index)
    {
        Node current = head;

        // Index of Node we are
        // currently looking at
        int count = 0; 
        while (current != null) 
        {
            if (count == index)
                return current.data;
            count++;
            current = current.next;
        }

        /* If we get to this line, the caller 
           was asking for a non-existent element 
           so we assert fail */
        Debug.Assert(false);
        return 0;
    }

    /* Given a reference to the head of a list 
       and an int, inserts a new Node on the 
       front of the list. */
    public void push(int new_data)
    {
        // 1\. Alloc the Node and put data
        Node new_Node = new Node(new_data);

        // 2\. Make next of new Node as head 
        new_Node.next = head;

        // 3\. Move the head to point to new Node
        head = new_Node;
    }

    // Driver code
    public static void Main(String[] args)
    {
        // Start with empty list 
        LinkedList llist = new LinkedList();

        // Use push() to construct list
        // 1->12->1->4->1
        llist.push(1);
        llist.push(4);
        llist.push(1);
        llist.push(12);
        llist.push(1);

        // Check the count function 
        Console.WriteLine("Element at index 3 is " + 
                           llist.GetNth(3));
    }
}

// This code is contributed by Arnab Kundu
```

**输出:**

```cs
Element at index 3 is 4
```

**时间复杂度:** O(n)

**方法 2-带递归:**

这个方法是 [MY_DOOM](https://auth.geeksforgeeks.org/user/MY_DOOM) 贡献的。

**算法:**

```cs
getnth(node, n)
1\. Initialize count = 0
2\. if count==n
     return node->data
3\. else
    return getnth(node->next, n-1)
```

**实现:**

## c#

```cs
// C# program to find n'th node in
// linked list using recursion
using System;

class GFG 
{
    // Link list node
    public class Node 
    {
        public int data;
        public Node next;
        public Node(int data)  
        { 
            this.data = data; 
        }
    }

    /* Given a reference (pointer to pointer) 
       to the head of a list and an int, push 
       a new node on the front of the list. */
    static Node push(Node head, int new_data)
    {
        // Allocate node
        Node new_node = new Node(new_data);

        // Put in the data 
        new_node.data = new_data;

        new_node.next = head;
        head = new_node;
        return head;
    }

    /* Takes head pointer of the linked list 
       and index as arguments and return data 
       at index*/
    static int GetNth(Node head, int n)
    {
        // Base Condition
        if (head == null)
            return -1;

        int count = 0;

        // If count equal too n return 
        // node.data
        // Test Condition
        if (count == n)
            return head.data;

        // Recursively decrease n and 
        // increase head to next pointer
        return GetNth(head.next, n - 1);
    }

    // Driver code
    public static void Main()
    {
        // Start with the empty list
        Node head = null;

        // Use push() to construct list
        // 1.12.1.4.1
        head = push(head, 1);
        head = push(head, 4);
        head = push(head, 1);
        head = push(head, 12);
        head = push(head, 1);

        // Check the count function 
        Console.Write("Element at index 3 is {0}",
                       GetNth(head, 3));
    }
}
// Code improvement by Aishwarya Mittal
// This code contributed by PrinciRaj1992
```

**输出:**

```cs
Element at index 3 is 4
```