# 用于从排序链表中删除重复项的 C# 程序

> 原文:[https://www . geesforgeks . org/c-program-for-remove-replications-from-sorted-link-list-2/](https://www.geeksforgeeks.org/c-program-for-removing-duplicates-from-a-sorted-linked-list-2/)

编写一个函数，接受按非递减顺序排序的列表，并从列表中删除任何重复的节点。该列表只能遍历一次。
例如，如果链接列表是 11->11->11->21->43->43->60，则 removeDuplicates()应该将列表转换为 11- > 21- > 43- > 60。

**算法:**
从头(或开始)节点遍历列表。遍历时，将每个节点与其下一个节点进行比较。如果下一个节点的数据与当前节点相同，则删除下一个节点。在删除节点之前，我们需要存储节点的下一个指针

**实现:**
removeDuplicates()之外的函数只是创建一个链表并测试 remove duplicates()。

## C#

```cs
// C# program to remove duplicates
// from a sorted linked list
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
            data = d; 
            next = null;
        }
    }

    void removeDuplicates()
    {
        // Another reference to head
        Node current = head;

        /* Pointer to store the next 
           pointer of a node to be deleted*/
        Node next_next;

        // Do nothing if the list is empty 
        if (head == null) 
            return;

        // Traverse list till the last node 
        while (current.next != null) 
        {

            // Compare current node with the 
            // next node 
            if (current.data == current.next.data) 
            {
                next_next = current.next.next;
                current.next = null;
                current.next = next_next;
            }

            // Advance if no deletion
            else 
                current = current.next;
        }
    }

    // Utility functions 

    // Inserts a new Node at front 
    // of the list. 
    public void push(int new_data)
    {
        /* 1 & 2: Allocate the Node &
                  Put in the data*/
        Node new_node = new Node(new_data);

        // 3\. Make next of new Node as head 
        new_node.next = head;

        // 4\. Move the head to point to new Node 
        head = new_node;
    }

    // Function to print linked list 
    void printList()
    {
        Node temp = head;
        while (temp != null)
        {
            Console.Write(temp.data + " ");
            temp = temp.next;
        } 
        Console.WriteLine();
    }

    // Driver code 
    public static void Main(String []args)
    {
        LinkedList llist = new LinkedList();
        llist.push(20);
        llist.push(13);
        llist.push(13);
        llist.push(11);
        llist.push(11);
        llist.push(11);

        Console.WriteLine(
                "List before removal of duplicates");
        llist.printList();

        llist.removeDuplicates();

        Console.WriteLine(
                "List after removal of elements");
        llist.printList();
    }
} 
// This code is contributed by 29AjayKumar 
```

**输出:**

```cs
Linked list before duplicate removal  11 11 11 13 13 20
Linked list after duplicate removal  11 13 20
```

**时间复杂度:** O(n)，其中 n 是给定链表中的节点数。

**递归方法:**

## C#

```cs
// C# Program to remove duplicates
// from a sorted linked list 
using System;

class GFG
{
    // Link list node 
    public class Node 
    { 
        public int data; 
        public Node next; 
    }; 

    // The function removes duplicates
    // from a sorted list 
    static Node removeDuplicates(Node head) 
    { 
        /* Pointer to store the pointer
           of a node to be deleted*/
        Node to_free; 

        // Do nothing if the list is empty
        if (head == null) 
            return null; 

        // Traverse the list till last node 
        if (head.next != null) 
        {        
            // Compare head node with next node 
            if (head.data == head.next.data) 
            { 
                /* The sequence of steps is important.
                   to_free pointer stores the next of 
                   head pointer which is to be deleted.*/
                to_free = head.next; 
                head.next = head.next.next;
                removeDuplicates(head);
            } 

            // This is tricky: only advance if no deletion 
            else
            { 
                removeDuplicates(head.next);
            } 
        } 
        return head;
    } 

    // UTILITY FUNCTIONS 
    /* Function to insert a node at the 
       beginning of the linked list */
    static Node push(Node head_ref,
                     int new_data) 
    { 
        // Allocate node 
        Node new_node = new Node();

        // Put in the data 
        new_node.data = new_data; 

        // Link the old list off the new node 
        new_node.next = (head_ref);     

        // Move the head to point to the 
        // new node 
        (head_ref) = new_node; 
        return head_ref;
    } 

    /* Function to print nodes in 
       a given linked list */
    static void printList(Node node) 
    { 
        while (node != null) 
        { 
            Console.Write(" " + node.data); 
            node = node.next; 
        } 
    } 

    // Driver code
    public static void Main(String []args)
    { 
        // Start with the empty list 
        Node head = null; 

        /* Let us create a sorted linked list
           to test the functions. Created 
           linked list will be 
           11.11.11.13.13.20 */
        head = push(head, 20); 
        head = push(head, 13); 
        head = push(head, 13); 
        head = push(head, 11); 
        head = push(head, 11); 
        head = push(head, 11);                                     

        Console.Write("Linked list before" + 
                      " duplicate removal "); 
        printList(head); 

        // Remove duplicates from linked list 
        head = removeDuplicates(head); 

        Console.Write("Linked list after" + 
                      " duplicate removal ");     
        printList(head);             
    }
}
// This code is contributed by PrinciRaj1992
```

**输出:**

```cs
Linked list before duplicate removal  11 11 11 13 13 20
Linked list after duplicate removal  11 13 20
```

**另一种方法:**创建一个指向每个元素第一次出现的指针和另一个将迭代到每个元素的指针 temp，当前一个指针的值不等于 temp 指针时，我们将前一个指针的指针设置为另一个节点的第一次出现。

下面是上述方法的实现:

## C#

```cs
// C# program to remove duplicates
// from a sorted linked list
using System;

class LinkedList
{  
    // Head of list
    public Node head;

    // Linked list Node
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

    // Function to remove duplicates
    // from the given linked list
    void removeDuplicates()
    {      
        // Two references to head temp 
        // will iterate to the whole 
        // Linked List prev will point 
        // towards the first occurrence 
        // of every element
        Node temp = head, prev = head;

        // Traverse list till the last node
        while (temp != null) 
        {           
           // Compare values of both pointers
           if(temp.data != prev.data)
           {             
                 /* if the value of prev is not 
                    equal to the value of temp 
                    that means there are no more 
                    occurrences of the prev data. 
                    So we can set the next of 
                    prev to the temp node.*/
                 prev.next = temp;
                 prev = temp;
           }

            /*Set the temp to the next node*/
            temp = temp.next;
        }

        /* This is the edge case if there are more 
           than one occurrences of the last element */
        if(prev != temp)
        {
            prev.next = null;
        }
    }

    // Utility functions 

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

    // Function to print linked list 
     void printList()
     {
         Node temp = head;
         while (temp != null)
         {
            Console.Write(temp.data + " ");
            temp = temp.next;
         }  
         Console.WriteLine();
     }

    // Driver code
    public static void Main(string []args)
    {
        LinkedList llist = new LinkedList();
        llist.push(20);
        llist.push(13);
        llist.push(13);
        llist.push(11);
        llist.push(11);
        llist.push(11);       
        Console.Write("List before ");
        Console.WriteLine("removal of duplicates");
        llist.printList();       
        llist.removeDuplicates();       
        Console.WriteLine(
                "List after removal of elements");
        llist.printList();
    }
} 
// This code is contributed by rutvik_56
```

**输出:**

```cs
List before removal of duplicates
11 11 11 13 13 20 
List after removal of elements
11 13 20 
```

**另一种方法:使用地图**

这个想法是推送地图中的所有值并打印其关键点。

下面是上述方法的实现:

## C#

```cs
// C# program for the above approach
using System;
using System.Collections.Generic;

public class Node
{
    public int data;
    public Node next;
    public Node()
    {
        data = 0;
        next = null;
    }
}
public class GFG
{    
    /* Function to insert a node at 
       the beginning of the linked list */
    static Node push(Node head_ref, 
                     int new_data)
    {       
        // Allocate node 
        Node new_node = new Node();

        // Put in the data 
        new_node.data = new_data;

        // Link the old list off 
        // the new node
        new_node.next = (head_ref);

        /* Move the head to point
           to the new node */
        head_ref = new_node;
        return head_ref;
    }

    /* Function to print nodes 
       in a given linked list */
    static void printList(Node node)
    {
        while (node != null) 
        {
            Console.Write(node.data + " ");
            node = node.next;
        }
    }

    // Function to remove duplicates
    static void removeDuplicates(Node head)
    {
        Dictionary<int, bool> track = 
                   new Dictionary<int, bool>();
        Node temp = head;
        while(temp != null)
        {
            if(!track.ContainsKey(temp.data))
            {
                Console.Write(temp.data + " ");
                track.Add(temp.data , true);
            }            
            temp = temp.next;
        }
    }

    // Driver Code
    static public void Main ()
    {
        Node head = null;

        /* Created linked list will be
           11->11->11->13->13->20 */
        head = push(head, 20);
        head = push(head, 13);
        head = push(head, 13);
        head = push(head, 11);
        head = push(head, 11);
        head = push(head, 11);

        Console.Write(
                "Linked list before duplicate removal ");
        printList(head);
        Console.Write(
                "Linked list after duplicate removal  ");
        removeDuplicates(head);
    }
}
// This code is contributed by rag2127
```

**输出:**

```cs
Linked list before duplicate removal 11 11 11 13 13 20
```

**时间复杂度:** O(节点数)

**空间复杂度:** O(节点数)

更多详情请参考[从排序链表](https://www.geeksforgeeks.org/remove-duplicates-from-a-sorted-linked-list/)中删除重复项的完整文章！