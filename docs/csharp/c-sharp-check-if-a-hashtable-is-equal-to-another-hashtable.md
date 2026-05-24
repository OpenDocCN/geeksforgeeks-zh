# C# |检查一个哈希表是否等于另一个哈希表

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-hashtable-等于另一个-hashtable/](https://www.geeksforgeeks.org/c-sharp-check-if-a-hashtable-is-equal-to-another-hashtable/)

哈希表类表示基于键的哈希代码组织的**键和值对**的集合。该键用于访问集合中的项。

**语法:**

```cs
myTable1.Equals(myTable2)

```

这里*我的表 1* 和*我的表 2* 是需要检查的两个哈希表。

下面给出一些例子，以便更好地理解实现:
**例子 1:**

```cs
// C# code to check if a Hashtable is
// equal to other Hashtable or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("g", "geeks");
        myTable.Add("c", "c++");
        myTable.Add("d", "data structures");
        myTable.Add("q", "quiz");

        // check if myTable is equal to myTable or not
        Console.WriteLine(myTable.Equals(myTable));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to check if a Hashtable is
// equal to other Hashtable or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating 1st Hashtable
        Hashtable myTable1 = new Hashtable();

        // Adding elements in Hashtable
        myTable1.Add("g", "geeks");
        myTable1.Add("c", "c++");
        myTable1.Add("d", "data structures");
        myTable1.Add("q", "quiz");

        // Creating 2nd Hashtable
        Hashtable myTable2 = new Hashtable();

        // Adding elements in Hashtable
        myTable2.Add("G", "geeksforgeeks");
        myTable2.Add("C", "C#");
        myTable2.Add("d", "data structures");
        myTable2.Add("q", "quiz");

        // check if both the Hashtables
        // are equal or not
        Console.WriteLine(myTable1.Equals(myTable2));
    }
}
```

**Output:**

```cs
False

```