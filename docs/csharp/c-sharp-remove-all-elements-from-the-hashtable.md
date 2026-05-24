# C# |从哈希表中移除所有元素

> 原文:[https://www . geesforgeks . org/c-sharp-从哈希表中移除所有元素/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-the-hashtable/)

哈希表类表示基于键的哈希代码组织的**键和值对**的集合。该键用于访问集合中的项。**哈希表。清除方法**用于从哈希表中移除所有元素。

**语法:**

```cs
myTable.Clear()

```

这里 *myTable* 是哈希表的名称。

**异常:**如果哈希表是只读的，这个方法将给出 *NotSupportedException* 。

**示例:**

```cs
// C# code to remove all elements
// from the Hashtable
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

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                                                  + myTable.Count);

        // To remove all elements from Hashtable
        myTable.Clear();

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                                                  + myTable.Count);

        // Adding elements in Hashtable
        myTable.Add("g", "geeks");
        myTable.Add("c", "c++");
        myTable.Add("d", "data structures");

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                                                  + myTable.Count);

        // To remove all elements from Hashtable
        myTable.Clear();

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                                                   + myTable.Count);
    }
}
```

**输出:**

```cs
Total number of entries in Hashtable : 4
Total number of entries in Hashtable : 0
Total number of entries in Hashtable : 3
Total number of entries in Hashtable : 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.clear?view=netframework-4.7.2)