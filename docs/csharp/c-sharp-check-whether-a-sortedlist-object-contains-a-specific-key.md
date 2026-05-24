# C# |检查 SortedList 对象是否包含特定键

> 原文:[https://www . geesforgeks . org/c-sharp-check-a-sorted list-object-contains-a-specific-key/](https://www.geeksforgeeks.org/c-sharp-check-whether-a-sortedlist-object-contains-a-specific-key/)

**排序列表。包含(对象)方法**用于检查排序列表对象是否包含特定的键。

**语法:**

```cs
public virtual bool Contains (object key);
```

这里，*键*是位于排序列表对象中的键。

**返回值:**如果 SortedList 对象包含具有指定键的元素，则该方法返回 *true* ，否则返回 *false*

**异常:**

*   **ArgumentNullException:** 如果密钥为空。
*   **无效操作异常:**如果比较器抛出异常。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to Check whether a SortedList
// object contains a specific key
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("1", "C++");
        mylist.Add("2", "Java");
        mylist.Add("3", "DSA");
        mylist.Add("4", "Python");
        mylist.Add("5", "C#");

        // Checking whether 4 is present
        // in SortedList or not
        Console.Write(mylist.Contains("4"));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to Check whether a SortedList
// object contains a specific key
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("First", "Ram");
        mylist.Add("Second", "Shyam");
        mylist.Add("Third", "Mohit");
        mylist.Add("Fourth", "Rohit");
        mylist.Add("Fifth", "Manish");

        // Checking whether 10 is present
        // in SortedList object or not
        Console.Write(mylist.Contains("Sixth"));
    }
}
```

**输出:**

```cs
False

```

**注:**

*   包含工具`IDictionary.Contains`。它的行为与*包含键*完全一样。
*   该方法使用二分搜索法算法；因此，这个方法是一个 O(log n)运算，其中 n 是 *[Count](https://www.geeksforgeeks.org/c-get-the-number-of-elements-contained-in-sortedlist/)* 。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.contains?view=netframework-4.7.2)