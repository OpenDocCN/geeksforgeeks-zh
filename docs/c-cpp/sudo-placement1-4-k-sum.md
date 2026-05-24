# Sudo 放置【1.4】| K 求和

> 原文:[https://www.geeksforgeeks.org/sudo-placement1-4-k-sum/](https://www.geeksforgeeks.org/sudo-placement1-4-k-sum/)

给定整数链表的头和整数 k，您的任务是修改链表如下:

*   考虑大小为 k 的组中的节点。在每个组中，用组和替换第一个节点的值。
*   此外，删除组中除第一个节点以外的元素。
*   在遍历过程中，如果链表中剩余的节点少于 k，那么也考虑剩余的节点。

**例:**

> **输入:** N = 6，K = 2
> 1->2->3->4->5->6
> **输出:** 3 7 11
> 我们用()表示 K 元素的分组。()中的元素被求和。
> 1->2->3->4->5->6->null
> (1->2->3->4->5->6->null
> (3)->3->4->5->6->null
> 3-> ->5->6->null
> 3->7->(5->6)->null
> 3->7->(11)->null
> 3->7->11->null

**方法:**在链表中插入给定的节点。在[这篇](https://www.geeksforgeeks.org/linked-list-set-2-inserting-a-node/)文章中已经讨论了插入的方法。插入节点后，从列表的开头开始迭代。将第一个节点标记为**温度**节点。对下一个 k-1 个节点进行迭代，并将 **sum** 变量中的节点相加。如果节点数小于 K，则用 sum 替换 temp 节点的数据，并将 temp 指向 NULL。如果有一个有 K 个节点的组，用 sum 替换 temp 的数据，并将 temp 移动到 K 个节点之后的节点。继续上述操作，直到温度指向空值。一旦 temp 到达末尾，它意味着所有 K 大小的组都已被遍历，并且该节点已被 K 大小的节点的总和替换。一旦替换操作完成，就可以打印这样形成的链表。在[这篇](https://www.geeksforgeeks.org/linked-list-set-1-introduction/)文章中已经讨论了链表的打印方法。

下面是上述方法的实现:

## C++

```cpp
// C++ program for
// SP - K Sum

#include <iostream>
using namespace std;

// structure for linked list
struct Node {
    long long data;
    Node* next;
};

// allocated new node
Node* newNode(int key)
{
    Node* temp = new Node;
    temp->data = key;
    temp->next = NULL;
    return temp;
}

// function to insert node in a Linked List
Node* insertNode(Node* head, int key)
{
    if (head == NULL)
        head = newNode(key);
    else
        head->next = insertNode(head->next, key);

    return head;
}

// traverse the node
// to print it
void print(Node* head)
{
    // traverse the linked list
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

// function to perform the following operation
void KSum(Node* head, int k)
{
    // initially pointing to start
    Node* temp = head;

    // iterate till end
    while (temp) {

        // dummy variable to store k
        long long count = k;

        // summation of nodes
        long long sum = 0;

        // currently at node from
        // which iteration is done
        Node* curr = temp;

        // till k nodes are visited and
        // last node is not visited
        while (count-- && curr) {
            // add to sum the node data
            sum = sum + curr->data;

            // move to the next node
            curr = curr->next;
        }

        // change pointer's data of temp to sum
        temp->data = sum;

        // move temp to next pointer
        temp->next = curr;

        // move temp to the next pointer
        temp = temp->next;
    }
}

// Driver Code
int main()
{

    Node* head = NULL;

    // inserts nodes in the linked list
    head = insertNode(head, 1);
    head = insertNode(head, 2);
    head = insertNode(head, 3);
    head = insertNode(head, 4);
    head = insertNode(head, 5);
    head = insertNode(head, 6);

    int k = 2;
    // Function call to perform the
    // given operations
    KSum(head, k);

    // print the linked list
    print(head);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program for
// SP - K Sum

import java.io.*;
import java.util.*;

// structure for linked list
class Node
{
    int data;
    Node next;
    Node(int key)
    {
        data = key;
        next = null;
    }
}

class GFG
{

// allocated new node
static Node head;

// function to insert node
// in a Linked List
public static Node insertNode(Node head, int key)
{
    if (head == null)
        head = new Node(key);
    else
        head.next = insertNode(head.next, key);

    return head;
}

// traverse the node
// to print it
public static void print(Node head)
{
    // traverse the linked list
    while (head != null)
    {
        System.out.print(head.data + " ");
        head = head.next;
    }
    System.out.println();
}

// function to perform
// the following operation
public static void KSum(Node head, int k)
{
    // initially pointing
    // to start
    Node temp = head;

    // iterate till end
    while (temp != null)
    {

        // dummy variable
        // to store k
        int count = k;

        // summation of nodes
        int sum = 0;

        // currently at node from
        // which iteration is done
        Node curr = temp;

        // till k nodes are visited and
        // last node is not visited
        while (count > 0 && curr != null)
        {
            // add to sum the node data
            sum = sum + curr.data;

            // move to the next node
            curr = curr.next;
            count--;
        }

        // change pointer's data
        // of temp to sum
        temp.data = sum;

        // move temp to
        // next pointer
        temp.next = curr;

        // move temp to
        // the next pointer
        temp = temp.next;
    }

    //return temp;
}

// Driver Code
public static void main(String args[])
{
     head = null;

    // inserts nodes in
    // the linked list
    head = insertNode(head, 1);
    head = insertNode(head, 2);
    head = insertNode(head, 3);
    head = insertNode(head, 4);
    head = insertNode(head, 5);
    head = insertNode(head, 6);

    int k = 2;

    // Function call to perform
    // the given operations
     KSum(head, k);

    // print the linked list
    print(head);
}
}
```

## 蟒蛇 3

```cpp
# Python program for
# SP - K Sum

# structure for linked list
class Node:
    def __init__(self, key):
        self.data = key
        self.next = None

# function to insert node in a Linked List
def insertNode(head: Node, key: int) -> Node:
    if head is None:
        head = Node(key)
    else:
        head.next = insertNode(head.next, key)

    return head

# traverse the node
# to print it
def Print(head: Node):

    # traverse the linked list
    while head:
        print(head.data, end = " ")
        head = head.next
    print()

# function to perform the following operation
def KSum(head: Node, k: int):

    # initially pointing to start
    temp = head

    # iterate till end
    while temp:

        # dummy variable to store k
        count = k

        # summation of nodes
        sum = 0

        # currently at node from
        # which iteration is done
        curr = temp

        # till k nodes are visited and
        # last node is not visited
        while count and curr:

            # add to sum the node data
            sum = sum + curr.data

            # move to the next node
            curr = curr.next
            count -= 1

        # change pointer's data of temp to sum
        temp.data = sum

        # move temp to next pointer
        temp.next = curr

        # move temp to the next pointer
        temp = temp.next

# Driver Code
if __name__ == "__main__":
    head = None

    # inserts nodes in the linked list
    head = insertNode(head, 1)
    head = insertNode(head, 2)
    head = insertNode(head, 3)
    head = insertNode(head, 4)
    head = insertNode(head, 5)
    head = insertNode(head, 6)

    k = 2

    # Function call to perform the
    # given operations
    KSum(head, k)

    # print the linked list
    Print(head)

# This code is contributed by
# sanjeev2552
```

## C#

```cpp
// C# program for SP - K Sum
using System;

// structure for linked list
public class Node
{
    public int data;
    public Node next;
    public Node(int key)
    {
        data = key;
        next = null;
    }
}

public class GFG
{

// allocated new node
static Node head;

// function to insert node
// in a Linked List
public static Node insertNode(Node head, int key)
{
    if (head == null)
        head = new Node(key);
    else
        head.next = insertNode(head.next, key);

    return head;
}

// traverse the node
// to print it
public static void print(Node head)
{
    // traverse the linked list
    while (head != null)
    {
        Console.Write(head.data + " ");
        head = head.next;
    }
    Console.WriteLine();
}

// function to perform
// the following operation
public static void KSum(Node head, int k)
{
    // initially pointing
    // to start
    Node temp = head;

    // iterate till end
    while (temp != null)
    {

        // dummy variable
        // to store k
        int count = k;

        // summation of nodes
        int sum = 0;

        // currently at node from
        // which iteration is done
        Node curr = temp;

        // till k nodes are visited and
        // last node is not visited
        while (count > 0 && curr != null)
        {
            // add to sum the node data
            sum = sum + curr.data;

            // move to the next node
            curr = curr.next;
            count--;
        }

        // change pointer's data
        // of temp to sum
        temp.data = sum;

        // move temp to
        // next pointer
        temp.next = curr;

        // move temp to
        // the next pointer
        temp = temp.next;
    }
    // return temp;
}

// Driver Code
public static void Main()
{
    head = null;

    // inserts nodes in
    // the linked list
    head = insertNode(head, 1);
    head = insertNode(head, 2);
    head = insertNode(head, 3);
    head = insertNode(head, 4);
    head = insertNode(head, 5);
    head = insertNode(head, 6);

    int k = 2;

    // Function call to perform
    // the given operations
    KSum(head, k);

    // print the linked list
    print(head);
}
}

/* This code contributed by PrinciRaj1992 */
```

## java 描述语言

```cpp
<script>
      // JavaScript program for SP - K Sum
      // structure for linked list
      class Node
      {
        constructor(key)
        {
          this.data = key;
          this.next = null;
        }
      }

      // allocated new node
      var head = null;

      // function to insert node
      // in a Linked List
      function insertNode(head, key)
      {
        if (head == null) head = new Node(key);
        else head.next = insertNode(head.next, key);

        return head;
      }

      // traverse the node
      // to print it
      function print(head)
      {

        // traverse the linked list
        while (head != null)
        {
          document.write(head.data + " ");
          head = head.next;
        }
        document.write("<br>");
      }

      // function to perform
      // the following operation
      function KSum(head, k)
      {

        // initially pointing
        // to start
        var temp = head;

        // iterate till end
        while (temp != null)
        {

          // dummy variable
          // to store k
          var count = k;

          // summation of nodes
          var sum = 0;

          // currently at node from
          // which iteration is done
          var curr = temp;

          // till k nodes are visited and
          // last node is not visited
          while (count > 0 && curr != null)
          {

            // add to sum the node data
            sum = sum + curr.data;

            // move to the next node
            curr = curr.next;
            count--;
          }

          // change pointer's data
          // of temp to sum
          temp.data = sum;

          // move temp to
          // next pointer
          temp.next = curr;

          // move temp to
          // the next pointer
          temp = temp.next;
        }

        // return temp;
      }

      // Driver Code
      head = null;

      // inserts nodes in
      // the linked list
      head = insertNode(head, 1);
      head = insertNode(head, 2);
      head = insertNode(head, 3);
      head = insertNode(head, 4);
      head = insertNode(head, 5);
      head = insertNode(head, 6);

      var k = 2;

      // Function call to perform
      // the given operations
      KSum(head, k);

      // print the linked list
      print(head);

      // This code is contributed by rdtank.
    </script>
```

**输出:**

```cpp
3 7 11
```