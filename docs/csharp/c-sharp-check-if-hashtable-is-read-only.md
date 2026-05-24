# C# |检查哈希表是否为只读

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-hashtable-只读/](https://www.geeksforgeeks.org/c-sharp-check-if-hashtable-is-read-only/)

**哈希表。IsReadOnly 属性**用于获取一个值，该值指示 ***[哈希表](https://www.geeksforgeeks.org/c-hashtable-class/)*** 是否为只读。

**语法:**

```cs
public virtual bool IsReadOnly { get; }
```

**返回值:**如果哈希表是只读的，该属性返回*真*，否则返回*假*。默认为*假*。

以下程序说明了上述属性:

**例 1:**

```cs
// C# code to check if Hashtable
// is read-only or not
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

        // Checking if Hashtable is read-only or not
        // this will return false
        Console.WriteLine(myTable.IsReadOnly);
    }
}
```

**Output:**

```cs
False

```

**例 2:**

```cs
// C# code to check if Hashtable
// is read-only or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("1", "C");
        myTable.Add("2", "C#");
        myTable.Add("3", "C++");
        myTable.Add("4", "HTML");
        myTable.Add("5", "CSS");

        // Checking if Hashtable is read-only or not
        // this will return false
        Console.WriteLine(myTable.IsReadOnly);
    }
}
```

**Output:**

```cs
False

```

**注:**

*   只读集合在创建后不允许添加、移除或修改元素。
*   只读集合只是一个带有防止修改集合的包装的集合。因此，如果对基础集合进行了更改，只读集合将反映这些更改。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . is readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.isreadonly?view=netframework-4.7.2)