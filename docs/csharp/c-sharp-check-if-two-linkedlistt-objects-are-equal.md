# C# |检查两个链表<t>对象是否相等</t>T3】

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-twin-linked list-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-linkedlistt-objects-are-equal/)

从 Object 类继承的 **Equals(Object)方法**用于检查指定的[链表<T>T3】对象是否等于另一个链表< T >对象。](https://www.geeksforgeeks.org/c-sharp-linkedlist-class/)

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to if a LinkedList object
// is equal to another LinkedList object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a LinkedList of Strings
        LinkedList<String> myList1 = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList1.AddLast("Geeks");
        myList1.AddLast("for");
        myList1.AddLast("Data Structures");
        myList1.AddLast("Noida");

        // Checking whether myList1 is
        // equal to itself or not
        Console.WriteLine(myList1.Equals(myList1));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# program to if a LinkedList object
// is equal to another LinkedList object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a LinkedList of Strings
        LinkedList<String> myList1 = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList1.AddLast("C");
        myList1.AddLast("C++");
        myList1.AddLast("Java");
        myList1.AddLast("C#");

        // Creating a LinkedList of Integers
        LinkedList<int> myList2 = new LinkedList<int>();

        // Adding nodes in LinkedList
        myList2.AddLast(2);
        myList2.AddLast(4);
        myList2.AddLast(6);
        myList2.AddLast(8);

        // Checking whether myList1 is
        // equal to myList2 or not
        Console.WriteLine(myList1.Equals(myList2));

        // Creating a LinkedList of Integers
        LinkedList<int> myList3 = new LinkedList<int>();

        // Assigning myList2 to myList3
        myList3 = myList2;

        // Checking whether myList3 is
        // equal to myList2 or not
        Console.WriteLine(myList3.Equals(myList2));
    }
}
```

**Output:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(Object)方法*检查引用是否相等。