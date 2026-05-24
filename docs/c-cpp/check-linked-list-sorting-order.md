# 检查链表是否排序(迭代和递归)

> 原文:[https://www . geesforgeks . org/check-link-list-sorting-order/](https://www.geeksforgeeks.org/check-linked-list-sorting-order/)

给定一个链表，任务是检查链表是否按降序排序？

**示例:**

```cpp
Input  : 8 -> 7 -> 5 -> 2 -> 1
Output : Yes
Explanation :
In given linked list, starting from head,
8 > 7 > 5 > 2 > 1\. So, it is sorted in reverse order

Input  : 24 -> 12 -> 9 -> 11 -> 8 -> 2
Output : No
```

**迭代方法:**从头到尾遍历链表。对于每个新遇到的元素，检查**节点- >数据>节点- >下一个- >数据**。如果为真，对每个节点执行相同的操作，否则返回 0 并打印“否”。

## C++

```cpp
// C++ program to check Linked List is sorted
// in descending order or not
#include <bits/stdc++.h>
using namespace std;

/* Linked list node */
struct Node
{
    int data;
    struct Node* next;
};

// function to Check Linked List is
// sorted in descending order or not
bool isSortedDesc(struct Node *head)
{
    if (head == NULL)
        return true;

    // Traverse the list till last node and return
    // false if a node is smaller than or equal
    // its next.
    for (Node *t=head; t->next != NULL; t=t->next)
       if (t->data <= t->next->data)
            return false;
    return true;
}

Node *newNode(int data)
{
   Node *temp = new Node;
   temp->next = NULL;
   temp->data = data;
}

// Driver program to test above
int main()
{
    struct Node *head = newNode(7);
    head->next = newNode(5);
    head->next->next = newNode(4);
    head->next->next->next = newNode(3);

    isSortedDesc(head) ? cout << "Yes" :
                         cout << "No";

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to check Linked List is sorted
// in descending order or not
class GFG
{

/* Linked list node */
static class Node
{
    int data;
    Node next;
};

// function to Check Linked List is
// sorted in descending order or not
static boolean isSortedDesc(Node head)
{
    if (head == null)
        return true;

    // Traverse the list till last node and return
    // false if a node is smaller than or equal
    // its next.
    for (Node t = head; t.next != null; t = t.next)
    if (t.data <= t.next.data)
            return false;
    return true;
}

static Node newNode(int data)
{
    Node temp = new Node();
    temp.next = null;
    temp.data = data;
    return temp;
}

// Driver Code
public static void main(String[] args)
{
    Node head = newNode(7);
    head.next = newNode(5);
    head.next.next = newNode(4);
    head.next.next.next = newNode(3);

    if(isSortedDesc(head))
        System.out.println("Yes");
    else
        System.out.println("No");
}
}

// This code is contributed by 29AjayKumar
```

## 蟒蛇 3

```cpp
# Python3 program to check Linked List is sorted
# in descending order or not
''' Linked list Node '''

class Node:
    def __init__(self, data):
        self.data = data;
        self.next = next;

# function to Check Linked List is
# sorted in descending order or not
def isSortedDesc(head):
    if (head == None):
        return True;

    # Traverse the list till last Node and return
    # False if a Node is smaller than or equal
    # its next.
    while(head.next != None):
        t = head;
        if (t.data <= t.next.data):
            return False;
        head = head.next
    return True;

def newNode(data):
    temp = Node(0);
    temp.next = None;
    temp.data = data;
    return temp;

# Driver Code
if __name__ == '__main__':
    head = newNode(7);
    head.next = newNode(5);
    head.next.next = newNode(4);
    head.next.next.next = newNode(3);

    if (isSortedDesc(head)):
        print("Yes");
    else:
        print("No");

# This code is contributed by 29AjayKumar
```

## C#

```cpp
// C# program to check Linked List is sorted
// in descending order or not
using System;

class GFG
{

/* Linked list node */
public class Node
{
    public int data;
    public Node next;
};

// function to Check Linked List is
// sorted in descending order or not
static bool isSortedDesc(Node head)
{
    if (head == null)
        return true;

    // Traverse the list till last node and
    // return false if a node is smaller than
    // or equal to its next.
    for (Node t = head;
              t.next != null; t = t.next)
    if (t.data <= t.next.data)
            return false;
    return true;
}

static Node newNode(int data)
{
    Node temp = new Node();
    temp.next = null;
    temp.data = data;
    return temp;
}

// Driver Code
public static void Main(String[] args)
{
    Node head = newNode(7);
    head.next = newNode(5);
    head.next.next = newNode(4);
    head.next.next.next = newNode(3);

    if(isSortedDesc(head))
        Console.WriteLine("Yes");
    else
        Console.WriteLine("No");
}
}

// This code is contributed by Rajput-Ji
```

## java 描述语言

```cpp
<script>

      // JavaScript program to recursively check Linked List
      // is sorted in descending order or not
      /* Linked list node */
      class Node {
        constructor() {
          this.data = 0;
          this.next = null;
        }
      }

      // function to Check Linked List is
      // sorted in descending order or not
      function isSortedDesc(head) {
        // Base cases
        if (head == null || head.next == null) return true;

        // Check first two nodes and recursively
        // check remaining.
        return head.data > head.next.data && isSortedDesc(head.next);
      }

      function newNode(data) {
        var temp = new Node();
        temp.next = null;
        temp.data = data;
        return temp;
      }

      // Driver code
      var head = newNode(7);
      head.next = newNode(5);
      head.next.next = newNode(4);
      head.next.next.next = newNode(3);

      if (isSortedDesc(head) == true) document.write("Yes");
      else document.write("No");

</script>
```

**Output:** 

```cpp
Yes
```

时间复杂度:O(N)，其中 N 是链表的长度。

**递归方法:**
递归检查**节点- >数据>节点- >下一个- >数据**，如果不是，返回 0，这是我们从递归中得出的终止条件，否则为下一个节点递归调用 Check_List 函数。

## C++

```cpp
// C++ program to recursively check Linked List
// is sorted in descending order or not
#include <bits/stdc++.h>
using namespace std;

/* Linked list node */
struct Node
{
    int data;
    struct Node* next;
};

// function to Check Linked List is
// sorted in descending order or not
bool isSortedDesc(struct Node *head)
{
    // Base cases
    if (head == NULL || head->next == NULL)
        return true;

    // Check first two nodes and recursively
    // check remaining.  
    return (head->data > head->next->data &&
        isSortedDesc(head->next));
}

Node *newNode(int data)
{
   Node *temp = new Node;
   temp->next = NULL;
   temp->data = data;
}

// Driver program to test above
int main()
{
    struct Node *head = newNode(7);
    head->next = newNode(5);
    head->next->next = newNode(4);
    head->next->next->next = newNode(3);

    isSortedDesc(head) ? cout << "Yes" :
                         cout << "No";

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to recursively check Linked List
// is sorted in descending order or not
class GfG {

/* Linked list node */
static class Node
{
    int data;
    Node next;
}

// function to Check Linked List is
// sorted in descending order or not
static boolean isSortedDesc(Node head)
{
    // Base cases
    if (head == null || head.next == null)
        return true;

    // Check first two nodes and recursively
    // check remaining.
    return (head.data > head.next.data && isSortedDesc(head.next));
}

static Node newNode(int data)
{
Node temp = new Node();
temp.next = null;
temp.data = data;
return temp;
}

// Driver program to test above
public static void main(String[] args)
{
    Node head = newNode(7);
    head.next = newNode(5);
    head.next.next = newNode(4);
    head.next.next.next = newNode(3);

    if(isSortedDesc(head) == true)
    System.out.println("Yes");
    else
    System.out.println("No");

}
}
```

## 蟒蛇 3

```cpp
# Python3 program to recursively check
# Linked List is sorted in descending
# order or not

# Linked list node
class Node:

    def __init__(self, data):

        self.data = data
        self.next = None

# Function to Check Linked List is
# sorted in descending order or not
def isSortedDesc(head):

    # Base cases
    if (head == None or head.next == None):
        return True

    # Check first two nodes and recursively
    # check remaining.  
    return (head.data > head.next.data and
           isSortedDesc(head.next))

def newNode(data):

   temp = Node(data)
   return temp

# Driver code
if __name__=="__main__":

    head = newNode(7)
    head.next = newNode(5)
    head.next.next = newNode(4)
    head.next.next.next = newNode(3)

    if isSortedDesc(head):
        print("Yes")
    else:
        print("No")

# This code is contributed by rutvik_56
```

## C#

```cpp
// C# program to recursively check Linked List
// is sorted in descending order or not
using System;

class GfG
{

/* Linked list node */
public class Node
{
    public int data;
    public Node next;
}

// function to Check Linked List is
// sorted in descending order or not
static bool isSortedDesc(Node head)
{
    // Base cases
    if (head == null || head.next == null)
        return true;

    // Check first two nodes and recursively
    // check remaining.
    return (head.data > head.next.data &&
                    isSortedDesc(head.next));
}

static Node newNode(int data)
{
    Node temp = new Node();
    temp.next = null;
    temp.data = data;
    return temp;
}

// Driver code
public static void Main(String[] args)
{
    Node head = newNode(7);
    head.next = newNode(5);
    head.next.next = newNode(4);
    head.next.next.next = newNode(3);

    if(isSortedDesc(head) == true)
    Console.WriteLine("Yes");
    else
    Console.WriteLine("No");

}
}

// This code contributed by Rajput-Ji
```

## java 描述语言

```cpp
<script>
    // Javascript program to recursively check Linked List
    // is sorted in descending order or not
    class Node
    {
        constructor(data) {
           this.next = null;
           this.data = data;
        }
    }

    // function to Check Linked List is
    // sorted in descending order or not
    function isSortedDesc(head)
    {
        // Base cases
        if (head == null || head.next == null)
            return true;

        // Check first two nodes and recursively
        // check remaining.
        return (head.data > head.next.data &&
                        isSortedDesc(head.next));
    }

    function newNode(data)
    {
        let temp = new Node(data);
        return temp;
    }

    let head = newNode(7);
    head.next = newNode(5);
    head.next.next = newNode(4);
    head.next.next.next = newNode(3);

    if(isSortedDesc(head) == true)
        document.write("Yes");
    else
        document.write("No");

    // This code is contributed by divyeshrabadiya07.
</script>
```

**Output:** 

```cpp
Yes
```