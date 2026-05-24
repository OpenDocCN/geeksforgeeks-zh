# C# |从链接列表中删除指定值的第一个匹配项

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-first-出现指定值-from-linked list/](https://www.geeksforgeeks.org/c-sharp-removing-first-occurrence-of-specified-value-from-linkedlistt/)

**Remove(T)** 方法用于从链接列表< **T** >中删除指定值的第一个出现。

**语法:**

```cs
public bool Remove (T value);

```

这里， ***值*** 是要从链接列表< **中移除的值** >。

**返回值:**如果成功移除包含值的元素，则该方法返回*真*，否则返回*假*。如果在原始链接列表< **T** >中没有找到值，该方法也返回 *False* 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the first
// occurrence of the specified
// value from LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // Adding nodes in LinkedList
        myList.AddLast(2);
        myList.AddLast(4);
        myList.AddLast(6);
        myList.AddLast(6);
        myList.AddLast(6);
        myList.AddLast(8);

        // To get the count of nodes in LinkedList
        // before removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }

        // Removing the first occurrence of
        // the specified value from LinkedList
        myList.Remove(6);

        // To get the count of nodes in LinkedList
        // after removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出:**

```cs
Total nodes in myList are : 6
2
4
6
6
6
8
Total nodes in myList are : 5
2
4
6
6
8

```

**例 2:**

```cs
// C# code to remove the first
// occurrence of the specified
// value from LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Strings
        LinkedList<String> myList = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList.AddLast("A");
        myList.AddLast("B");
        myList.AddLast("C");
        myList.AddLast("D");
        myList.AddLast("E");

        // To get the count of nodes in LinkedList
        // before removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }

        // Removing the first occurrence of
        // the specified value from LinkedList
        // As "H" is not in LinkedList, so
        // there will be no change  in the LinkedList
        myList.Remove("H");

        // To get the count of nodes in LinkedList
        // after removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
Total nodes in myList are : 5
A
B
C
D
E
Total nodes in myList are : 5
A
B
C
D
E

```

**注意:**此方法执行线性搜索。因此，此方法为 O(n)运算，其中 n 为**计数**。

**参考:**
[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . remove？view = net framework-4 . 7 . 2 # System _ Collections _ Generic _ LinkedList _ 1 _ Remove _ 0 _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.remove?view=netframework-4.7.2# System_Collections_Generic_LinkedList_1_Remove__0_)