# 用于从未排序的链表中删除重复项的 C# 程序

> 原文:[https://www . geesforgeks . org/c-program-for-remove-replications-from-unsorted-link-list/](https://www.geeksforgeeks.org/c-program-for-removing-duplicates-from-an-unsorted-linked-list/)

编写一个 removeDuplicates()函数，该函数获取一个列表并从列表中删除任何重复的节点。列表未排序。
例如，如果链接列表是 12->11->12->21->41->43->21，则 removeDuplicates()应该将列表转换为 12->11->21->41->43。

**方法 1(使用两个循环):**
这是使用两个循环的简单方法。外环用于逐个拾取元素，内环将拾取的元素与其余元素进行比较。
感谢 Gaurav Saxena 对编写这段代码的帮助。

## C#

```cs
// C# program to remove duplicates from
// unsorted linked list
using System;
class List_ 
{
    Node head;
    class Node 
    {
        public int data;
        public Node next;
        public Node(int d)
        {
            data = d;
            next = null;
        }
    }

    /* Function to remove duplicates from
       an unsorted linked list */
    void remove_duplicates()
    {
        Node ptr1 = null, 
             ptr2 = null, dup = null;
        ptr1 = head;

        // Pick elements one by one 
        while (ptr1 != null && 
               ptr1.next != null) 
        {
            ptr2 = ptr1;

            /* Compare the picked element with 
               rest of the elements */
            while (ptr2.next != null) 
            {
                // If duplicate then delete it 
                if (ptr1.data == ptr2.next.data) 
                {
                    // sequence of steps is important here
                    dup = ptr2.next;
                    ptr2.next = ptr2.next.next;
                }
                else
                {
                    ptr2 = ptr2.next;
                }
            }
            ptr1 = ptr1.next;
        }
    }

    void printList(Node node)
    {
        while (node != null) 
        {
            Console.Write(node.data + " ");
            node = node.next;
        }
    }

    // Driver Code
    public static void Main(String[] args)
    {
        List_ list = new List_();
        list.head = new Node(10);
        list.head.next = new Node(12);
        list.head.next.next = new Node(11);
        list.head.next.next.next = new Node(11);
        list.head.next.next.next.next = new Node(12);
        list.head.next.next.next.next.next = new Node(11);
        list.head.next.next.next.next.next.next
            = new Node(10);

        Console.WriteLine(
                "Linked List_ before removing duplicates : ");
        list.printList(list.head);

        list.remove_duplicates();
        Console.WriteLine("");
        Console.WriteLine(
                "Linked List_ after removing duplicates : ");
        list.printList(list.head);
    }
}
// This code is contributed by gauravrajput1
```

**输出:**

```cs
Linked list before removing duplicates:
10 12 11 11 12 11 10 
Linked list after removing duplicates:
10 12 11
```

时间复杂性:O(n^2)

**方法 2(使用排序):**
一般来说，合并排序是最适合高效排序链表的排序算法。
1)使用合并排序对元素进行排序。我们很快会写一篇关于排序链表的文章。O(nLogn)
2)使用[算法在线性时间内移除重复项，以移除排序链表中的重复项。O(n)](https://www.geeksforgeeks.org/remove-duplicates-from-a-sorted-linked-list/)
请注意，这种方法没有保留元素的原始顺序。
**时间复杂度** : O(nLogn)

**方法 3(使用哈希):**
我们从头到尾遍历链接列表。对于每一个新遇到的元素，我们检查它是否在哈希表中:如果是，我们删除它；否则我们把它放到散列表中。

## C#

```cs
// C# program to remove duplicates
// from unsorted linkedlist
using System;
using System.Collections.Generic;

class removeDuplicates
{
    class node 
    {
        public int val;
        public node next;

        public node(int val) 
        {
            this.val = val;
        }
}

// Function to remove duplicates from a
// unsorted linked list 
static void removeDuplicate(node head) 
{    
    // Hash to store seen values
    HashSet<int> hs = new HashSet<int>();

    // Pick elements one by one 
    node current = head;
    node prev = null;
    while (current != null) 
    {
        int curval = current.val;

        // If current value is seen before
        if (hs.Contains(curval))
        {
            prev.next = current.next;
        }
        else 
        {
            hs.Add(curval);
            prev = current;
        }
        current = current.next;
    }
}

// Function to print nodes in a 
// given linked list 
static void printList(node head) 
{
    while (head != null) 
    {
        Console.Write(head.val + " ");
        head = head.next;
    }
}

// Driver code
public static void Main(String[] args) 
{   
    // The constructed linked list is:
    // 10->12->11->11->12->11->10
    node start = new node(10);
    start.next = new node(12);
    start.next.next = new node(11);
    start.next.next.next = new node(11);
    start.next.next.next.next = new node(12);
    start.next.next.next.next.next = new node(11);
    start.next.next.next.next.next.next = new node(10);

    Console.WriteLine("Linked list before removing " +
                      "duplicates :");
    printList(start);
    removeDuplicate(start);

    Console.WriteLine("Linked list after removing " + 
                      "duplicates :");
    printList(start);
}
}
// This code is contributed by amal kumar choubey
```

**输出:**

```cs
Linked list before removing duplicates:
10 12 11 11 12 11 10 
Linked list after removing duplicates:
10 12 11
```

感谢 bearwang 提出这个方法。
**时间复杂度:**平均 O(n)(假设哈希表访问时间平均为 O(1))。

更多详细信息，请参考完整文章[从未排序的链表](https://www.geeksforgeeks.org/remove-duplicates-from-an-unsorted-linked-list/)中删除重复项！