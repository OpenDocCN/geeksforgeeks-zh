# C# |检查链接列表中是否有值

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-value-in-linked list/](https://www.geeksforgeeks.org/c-sharp-check-if-a-value-is-in-linkedlistt/)

**链接列表<T1**T5。Contains(T) 方法用于检查一个值是否在链表< T >中。

**语法:**

```cs
public bool Contains (T value);

```

这里， ***值*** 是链接列表中要定位的值< **T** >。对于引用类型，该值可以为 null。

**返回值:**如果在链表中找到值，该方法返回 ***真*** ，否则返回 ***假*** 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to check if a
// value is in LinkedList
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

        // To check if a value is in LinkedList
        Console.WriteLine(myList.Contains("B"));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to check if a
// value is in LinkedList
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
        myList.AddLast(1);
        myList.AddLast(2);
        myList.AddLast(3);
        myList.AddLast(4);
        myList.AddLast(5);

        // To check if a value is in LinkedList
        Console.WriteLine(myList.Contains(8));
    }
}
```

**输出:**

```cs
False

```

**注意:**此方法执行线性搜索。因此，这个方法是一个 **O(n)** 运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.contains?view=netframework-4.7.2)