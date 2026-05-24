# C# |获取排序列表对象的键列表

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-list-object-of-sorted-list-object/](https://www.geeksforgeeks.org/c-sharp-getting-the-list-of-keys-of-a-sortedlist-object/)

***排序列表。**获取关键字列表方法*用于获取排序列表对象中的关键字列表。

**语法:**

```cs
public virtual System.Collections.IList GetKeyList ();
```

**返回值:**返回一个包含 SortedList 对象中的键的 [IList](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=netframework-4.7.2) 对象。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code for getting the keys
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
        // using GetKeyList method
        IList klist = mylist.GetKeyList();

        // Prints the list of keys
        Console.WriteLine("Key List");

        for (int i = 0; i < mylist.Count; i++)
            Console.WriteLine(klist[i]);
    }
}
```

**输出:**

```cs
Key List
1
2
3
4
5

```

**例 2:**

```cs
// C# code for getting the keys
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
        // using GetKeyList method
        IList klist = mylist.GetKeyList();

        // Prints the list of keys
        Console.WriteLine("Key List");

        // will print the keys in sorted order
        for (int i = 0; i < mylist.Count; i++)
            Console.WriteLine(klist[i]);
    }
}
```

**输出:**

```cs
Key List
Fifth
First
Fourth
Second
Third

```

**注:**

*   返回的 [IList](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=netframework-4.7.2) 对象是 SortedList 对象的键的只读视图。对底层 SortedList 所做的修改会立即反映在 IList 中。
*   返回的 IList 的元素按照与 SortedList 的键相同的顺序进行排序。
*   这个方法类似于属性，但是返回一个 IList 对象，而不是一个 ICollection 对象。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . getkey list？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.getkeylist?view=netframework-4.7.2)