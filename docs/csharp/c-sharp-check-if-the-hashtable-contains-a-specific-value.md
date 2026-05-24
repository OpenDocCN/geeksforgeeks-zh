# C# |检查哈希表是否包含特定值

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-hashtable-contains-specific-value/](https://www.geeksforgeeks.org/c-sharp-check-if-the-hashtable-contains-a-specific-value/)

哈希表类表示基于键的哈希代码组织的**键和值对**的集合。该键用于访问集合中的项。*哈希表。ContainsValue(Object)方法*用于检查哈希表是否包含特定的值。

**语法:**

```cs
public virtual bool ContainsValue(object value);

```

**参数:**

> **值:**类型*系统的值。对象*在哈希表中定位。*值*可以为空。

**返回类型:**如果哈希表包含具有指定*值*的元素，该方法返回*真*，否则返回*假*。该方法的返回类型为*系统。布尔*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to check if the HashTable
// contains a specific Value
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

        // check if the HashTable contains
        // the required Value or not.
        if (myTable.ContainsValue("c++"))
            Console.WriteLine("myTable contains the Value");
        else
            Console.WriteLine("myTable doesn't contain the Value");
    }
}
```

**Output:**

```cs
myTable contains the Value

```

**例 2:**

```cs
// C# code to check if the HashTable
// contains a specific Value
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

        // check if the HashTable contains
        // the required Value or not.
        if (myTable.ContainsKey("Ocean"))
            Console.WriteLine("myTable contains the Value");
        else
            Console.WriteLine("myTable doesn't contain the Value");
    }
}
```

**Output:**

```cs
myTable doesn't contain the Value

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . contains value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.containsvalue?view=netframework-4.7.2)