# C# |检查哈希表是否同步(线程安全)

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-hashtable-is-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-hashtable-is-synchronized-thread-safe/)

**哈希表。IsSynchronized Property** 用于获取一个值，该值指示对 ***[哈希表](https://www.geeksforgeeks.org/c-hashtable-class/)*** 的访问是否同步(线程安全)。

**语法:**

```cs
public virtual bool IsSynchronized { get; }
```

**返回值:**如果对哈希表的访问是同步的(线程安全的)，该属性返回 *true* ，否则返回 *false* 。默认为*假*。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to check if Hashtable
// Is Synchronized or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // create and initialize Hashtable 
        // using Add() method 
        Hashtable has1 = new Hashtable(); 

        has1.Add("1", "Welcome"); 
        has1.Add("2", "to"); 
        has1.Add("3", "geeks"); 
        has1.Add("4", "for"); 
        has1.Add("5", "geeks"); 

        // Creates a synchronized
        // wrapper around the Hashtable.
        Hashtable smyTable = Hashtable.Synchronized(has1);

        // Displays the synchronization 
        // status of both Hashtables.
        Console.WriteLine("has1 is {0}.", has1.IsSynchronized ? 
                                "Synchronized" : "Not Synchronized");

        Console.WriteLine("smyTable is {0}.", smyTable.IsSynchronized ?
                                  "Synchronized" : "Not Synchronized");
    }
}
```

**Output:**

```cs
has1 is Not Synchronized.
smyTable is Synchronized.

```

**例 2:**

```cs
// C# code to check if Hashtable
// Is Synchronized or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("G", "Geeks");
        myTable.Add("C", "C#");
        myTable.Add("D", "Data Structures");
        myTable.Add("Q", "Quiz");

        // Checking if Hashtable is
        // synchronized (thread safe)
        Console.WriteLine(myTable.IsSynchronized);
    }
}
```

**Output:**

```cs
False

```

**注意:**一个 Hashtable 可以同时支持一个 writer 和多个 readers。为了支持多个编写器，所有操作都必须通过 Synchronized 方法返回的包装器来完成。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.issynchronized?view=netframework-4.7.2)