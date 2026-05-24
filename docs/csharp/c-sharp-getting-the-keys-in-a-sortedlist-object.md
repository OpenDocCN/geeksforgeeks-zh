# C# |获取排序列表对象中的键

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-key-in-a-sorted list-object/](https://www.geeksforgeeks.org/c-sharp-getting-the-keys-in-a-sortedlist-object/)

**排序列表。键属性**用于获取排序列表对象中的键。

**语法:**

```cs
public virtual System.Collections.ICollection Keys { get; }
```

**属性值:**包含排序列表对象中的键的集合对象。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to get an ICollection containing
// the keys in the SortedList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedList
        SortedList mylist = new SortedList();

        // Adding elements in SortedList
        mylist.Add("4", "Even");
        mylist.Add("9", "Odd");
        mylist.Add("5", "Odd and Prime");
        mylist.Add("2", "Even and Prime");

        // Get a collection of the keys.
        ICollection c = mylist.Keys;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + ": " + mylist[str]);
    }
}
```

**Output:**

```cs
2: Even and Prime
4: Even
5: Odd and Prime
9: Odd

```

**例 2:**

```cs
// C# code to get an ICollection containing
// the keys in the SortedList.
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedList
        SortedList mylist = new SortedList();

        // Adding elements in SortedList
        mylist.Add("India", "Country");
        mylist.Add("Chandigarh", "City");
        mylist.Add("Mars", "Planet");
        mylist.Add("China", "Country");

        // Get a collection of the keys.
        ICollection c = mylist.Keys;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + ": " + mylist[str]);
    }
}
```

**Output:**

```cs
Chandigarh: City
China: Country
India: Country
Mars: Planet

```

**注:**

*   ICollection 对象是 SortedList 对象的键的只读视图。对基础 SortedList 所做的修改会立即反映在 ICollection 中。
*   ICollection 的元素按照与 SortedList 的键相同的顺序进行排序。
*   该属性类似于 GetKeyList 方法，但返回一个 ICollection 对象，而不是 IList 对象。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . keys？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.keys?view=netframework-4.7.2)