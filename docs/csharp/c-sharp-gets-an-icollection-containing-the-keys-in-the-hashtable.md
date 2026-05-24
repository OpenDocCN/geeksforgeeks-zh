# C# |获取一个包含哈希表

中的键的集合

> 原文:[https://www . geesforgeks . org/c-sharp-get-an-I collection-包含哈希表中的键/](https://www.geeksforgeeks.org/c-sharp-gets-an-icollection-containing-the-keys-in-the-hashtable/)

***哈希表。钥匙属性*** 用于获取一个[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)，该集合包含 **[哈希表](https://www.geeksforgeeks.org/c-hashtable-class/)** 中的钥匙。

**语法:**

```cs
public virtual System.Collections.ICollection Keys { get; }
```

**返回值:**该属性返回一个包含哈希表中键的 ICollection。

**注:**

*   ICollection 中的键顺序未指定。
*   检索该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to get an ICollection containing
// the keys in the Hashtable.
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("4", "Even");
        myTable.Add("9", "Odd");
        myTable.Add("5", "Odd and Prime");
        myTable.Add("2", "Even and Prime");

        // Get a collection of the keys.
        ICollection c = myTable.Keys;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + ": " + myTable[str]);
    }
}
```

**Output:**

```cs
5: Odd and Prime
9: Odd
2: Even and Prime
4: Even

```

**例 2:**

```cs
// C# code to get an ICollection containing
// the keys in the Hashtable.
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

        // Get a collection of the keys.
        ICollection c = myTable.Keys;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + ": " + myTable[str]);
    }
}
```

**Output:**

```cs
Chandigarh: City
India: Country
China: Country
Mars: Planet

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . keys？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.keys?view=netframework-4.7.2)