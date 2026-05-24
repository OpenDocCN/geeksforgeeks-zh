# C# 检查哈希表是否包含特定的键

> 原文：[https://www.geeksforgeeks.org/c-sharp-check-if-the-hashtable-contains-a-specific-key/](https://www.geeksforgeeks.org/c-sharp-check-if-the-hashtable-contains-a-specific-key/)

`Hashtable`类表示基于键的哈希代码组织的`键和值对`的集合。该键用于访问集合中的项。`Hashtable.ContainsKey(Object)`方法用于检查哈希表是否包含特定的键。

**语法：**

```cs
public virtual bool ContainsKey(object key);
```

**参数：**

> **key**：类型为`System.Object`，在哈希表中定位的键。

**返回类型：** 如果哈希表包含具有指定键的元素，则返回`true`，否则返回`false`。该方法的返回类型为`System.Boolean`。

**异常：** 如果`key`为空，这个方法可以抛出`ArgumentNullException`。

下面给出了一些例子，以便更好地理解实现：

**例 1：**

```cs
// C# code to check if the HashTable
// contains a specific key
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
        // the required key or not.
        if (myTable.ContainsKey("c"))
            Console.WriteLine("myTable contains the key");
        else
            Console.WriteLine("myTable doesn't contain the key");
    }
}
```

**Output：**

```cs
myTable contains the key
```

**例 2：**

```cs
// C# code to check if the HashTable
// contains a specific key
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
        // the required key or not.
        if (myTable.ContainsKey("Earth"))
            Console.WriteLine("myTable contains the key");
        else
            Console.WriteLine("myTable doesn't contain the key");
    }
}
```

**Output：**

```cs
myTable doesn't contain the key
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.containskey?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.containskey?view=netframework-4.7.2)