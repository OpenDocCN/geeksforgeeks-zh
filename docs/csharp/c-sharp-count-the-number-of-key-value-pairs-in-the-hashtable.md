# C# |计算哈希表

中键/值对的数量

> 原文:[https://www . geesforgeks . org/c-sharp-计算哈希表中键值对的数量/](https://www.geeksforgeeks.org/c-sharp-count-the-number-of-key-value-pairs-in-the-hashtable/)

哈希表类表示基于键的哈希代码组织的**键和值对**的集合。该键用于访问集合中的项。**哈希表。计数属性**用于获取哈希表中包含的键/值对的总数。

**语法:**

```cs
myTable.Count

```

这里， *myTable* 是哈希表的名称。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the number of key-and-value
// pairs contained in the Hashtable.
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("2", "Even & Prime");
        myTable.Add("3", "Odd & Prime");
        myTable.Add("4", "Even & non-prime");
        myTable.Add("9", "Odd & non-prime");

        // To get the number of key-and-value
        // pairs contained in the Hashtable.
        Console.WriteLine(myTable.Count);
    }
}
```

**Output:**

```cs
4

```

**例 2:**

```cs
// C# code to get the number of key-and-value
// pairs contained in the Hashtable.
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an empty Hashtable
        Hashtable myTable = new Hashtable();

        // To get the number of key-and-value
        // pairs contained in the Hashtable.
        Console.WriteLine(myTable.Count);
    }
}
```

**Output:**

```cs
0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.count?view=netframework-4.7.2)