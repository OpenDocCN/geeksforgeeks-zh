# C# |获取一个包含哈希表

中值的集合

> 原文:[https://www . geesforgeks . org/c-sharp-get-an-I collection-包含哈希表中的值/](https://www.geeksforgeeks.org/c-sharp-gets-an-icollection-containing-the-values-in-the-hashtable/)

***哈希表。值属性*** 用于获取包含 **[哈希表](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.values?view=netframework-4.7.2)** 中值的[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)。

**语法:**

```cs
public virtual System.Collections.ICollection Values { get; }
```

**返回值:**该属性返回一个包含哈希表中值的 ICollection。

**注:**

*   ICollection 中值的顺序未指定。
*   检索该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to get an ICollection containing
// the values in the Hashtable.
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

        // Get a collection of the values
        ICollection c = myTable.Values;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + myTable[str]);
    }
}
```

**Output:**

```cs
data structures
c++
quiz
geeks

```

**例 2:**

```cs
// C# code to get an ICollection containing
// the values in the Hashtable.
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("India", "Country");
        myTable.Add("Chandigarh", "City");
        myTable.Add("Mars", "Planet");
        myTable.Add("China", "Country");

        // Get a collection of the values
        ICollection c = myTable.Values;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + myTable[str]);
    }
}
```

**Output:**

```cs
City
Country
Country
Planet

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . values？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.values?view=netframework-4.7.2)