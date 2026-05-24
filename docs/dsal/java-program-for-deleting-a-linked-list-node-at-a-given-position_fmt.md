# 删除给定位置链表节点的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-for-deleting-a-linked-list-node-at-a-given-position/](https://www.geeksforgeeks.org/java-program-for-deleting-a-linked-list-node-at-a-given-position/)

给定一个单链表和一个位置，删除给定位置的链表节点。

**例：**

```
Input: position = 1, Linked List = 8->2->3->1->7
Output: Linked List =  8->3->1->7

Input: position = 0, Linked List = 8->2->3->1->7
Output: Linked List = 2->3->1->7
```

如果要删除的节点是根，只需将其删除即可。要删除中间节点，我们必须有一个指向要删除的节点之前的节点的指针。所以如果位置不为零，我们运行一个位置循环 1 次，得到一个指向前一个节点的指针。

以下是上述想法的实现。

## Java

```java
// Java program to delete a linked list node at a given position
class LinkedList {
    Node head; // head of the list

    /* Linked list node */
    class Node {
        int data;
        Node next;
        Node(int d)
        {
            data = d;
            next = null;
        }
    }

    /* Inserts a new Node at front of the list. */
    public void push(int new_data)
    {
        Node new_node = new Node(new_data);
        new_node.next = head;
        head = new_node;
    }

    /* Given a reference (pointer to pointer) to the head of a list
       and a position, deletes the node at the given position */
    void deleteNode(int position)
    {
        // If linked list is empty
        if (head == null)
            return;

        // Store head node
        Node temp = head;

        // If head needs to be removed
        if (position == 0) {
            head = temp.next; // Change head
            return;
        }

        // Find previous node of the node to be deleted
        for (int i = 0; temp != null && i < position - 1; i++)
            temp = temp.next;

        // If position is more than number of nodes
        if (temp == null || temp.next == null)
            return;

        // Node temp->next is the node to be deleted
        // Store pointer to the next of the node to be deleted
        Node next = temp.next.next;

        temp.next = next; // Unlink the deleted node from list
    }

    /* Utility function to print a linked list */
    void printList()
    {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }

    /* Driver program to test above functions */
    public static void main(String args[])
    {
        LinkedList llist = new LinkedList();

        llist.push(7);
        llist.push(1);
        llist.push(3);
        llist.push(2);
        llist.push(8);

        System.out.println("Created Linked List: ");
        llist.printList();
        llist.deleteNode(4); // Delete node at position 4

        System.out.println("\nLinked List after Deletion at position 4: ");
        llist.printList();
    }
}
```

**输出：**

```
Created Linked List: 
 8  2  3  1  7 
Linked List after Deletion at position 4: 
 8  2  3  1 
```

详情请参考[删除给定位置](https://www.geeksforgeeks.org/delete-a-linked-list-node-at-a-given-position/)的链表节点整篇文章！