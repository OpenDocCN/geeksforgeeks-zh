# C# |获取排序列表对象的值列表

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-list-object-of-sorted-list-object 的值列表/](https://www.geeksforgeeks.org/c-sharp-getting-the-list-of-values-of-a-sortedlist-object/)

**排序列表。GetValueList 方法**用于获取 SortedList 对象中的键列表。

**语法:**

```cs
public virtual System.Collections.IList GetValueList ();
```

**返回值:**返回一个包含 SortedList 对象中值的 *[IList](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=netframework-4.7.2)* 对象。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code for getting the values
// in a SortedList object
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("1", "C++");
        mylist.Add("2", "Java");
        mylist.Add("3", "DSA");
        mylist.Add("4", "Python");
        mylist.Add("5", "C#");

        // taking an IList and
        // using GetValueList method
        IList vlist = mylist.GetValueList();

        // Prints the list of keys
        Console.WriteLine("Value Stored in SortedList:");

        // will print the values in Sorted Order
        for (int i = 0; i < mylist.Count; i++)
            Console.WriteLine(vlist[i]);
    }
}
```

**Output:**

```cs
Value Stored in SortedList:
C++
Java
DSA
Python
C#

```

**例 2:**

```cs
// C# code for getting the values
// in a SortedList object
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("First", "Ram");
        mylist.Add("Second", "Shyam");
        mylist.Add("Third", "Mohit");
        mylist.Add("Fourth", "Rohit");
        mylist.Add("Fifth", "Manish");

        // taking an IList and
        // using GetValueList method
        IList vlist = mylist.GetValueList();

        // Prints the list of keys
        Console.WriteLine("Value Stored in SortedList:");

        // will print the values in Sorted Order
        for (int i = 0; i < mylist.Count; i++)
            Console.WriteLine(vlist[i]);
    }
}
```

**Output:**

```cs
Value Stored in SortedList:
Manish
Ram
Rohit
Shyam
Mohit

```

**注:**

*   返回的 IList 对象是 SortedList 对象的值的只读视图。对底层 SortedList 所做的修改会立即反映在 IList 中。
*   返回的 IList 的元素按照与 SortedList 的值相同的顺序进行排序。
*   该方法类似于 *[值](https://www.geeksforgeeks.org/c-getting-the-values-in-a-sortedlist-object/)* 属性，但返回一个 *IList* 对象，而不是 *ICollection* 对象。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . getvaluelist？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.getvaluelist?view=netframework-4.7.2)