# C# |检查哈希表是否有固定大小

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-hashtable-has-a-fixed-size/](https://www.geeksforgeeks.org/c-sharp-check-if-hashtable-has-a-fixed-size/)

**哈希表。IsFixedSize Property** 用于获取一个值，该值指示 ***[哈希表](https://www.geeksforgeeks.org/c-hashtable-class/)*** 是否具有固定大小。

**语法:**

```cs
public virtual bool IsFixedSize { get; }
```

**返回值:**如果哈希表的大小固定，该属性返回 *true* ，否则返回 *false* 。默认为*假*。

以下程序说明了上述属性:

**例 1:**

```cs
// C# code to check if Hashtable
// has a fixed size
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

        // Checking if Hashtable has a fixed size
        // this will return false
        Console.WriteLine(myTable.IsFixedSize);
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
// has a fixed size
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable and 
        // giving it a size of 4
        Hashtable myTable = new Hashtable(4);

        // Adding elements in Hashtable
        myTable.Add("1", "C");
        myTable.Add("2", "C#");
        myTable.Add("3", "DS");
        myTable.Add("4", "Java");
        myTable.Add("5","HTML");
        myTable.Add("6", "CSS");

        // Checking if Hashtable has a fixed size
        // this will return false
        Console.WriteLine(myTable.IsFixedSize);
    }
}
```

**Output:**

```cs
False

```

**注:**

*   具有固定大小的集合不允许在创建集合后添加或移除元素，但允许修改现有元素。
*   固定大小的集合只是一个带有防止添加和移除元素的包装的集合。因此，如果对基础集合进行了更改，包括添加或移除元素，固定大小的集合将反映这些更改。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . isfixedsize？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.isfixedsize?view=netframework-4.7.2)