# C# |获取排序列表对象指定索引处的键

> 原文:[https://www . geeksforgeeks . org/c-sharp-按指定的排序索引获取关键字列表对象/](https://www.geeksforgeeks.org/c-sharp-getting-the-key-at-the-specified-index-of-a-sortedlist-object/)

**排序列表。GetKey(Int32)方法**用于获取 SortedList 对象指定索引处的键。

**语法:**

```cs
public virtual object GetKey (int index);
```

这里，*索引*是要获取的密钥的从零开始的索引。

**返回值:**该方法返回 SortedList 对象指定索引处的键。

**异常:**如果*索引*在 SortedList 对象的有效索引范围之外，此方法将抛出`ArgumentOutOfRangeException` 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get the key at
// the specified index of a
// SortedList object
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("key1", "C++");
        mylist.Add("key2", "Java");
        mylist.Add("key3", "DSA");
        mylist.Add("key4", "Python");
        mylist.Add("key5", "C#");

        // storing the value of
        // index that needed by
        // used into a variable
        int i = 2;

        // getting the key at index 2
        Console.WriteLine("Key at index {0} is {1}",
                          i, mylist.GetKey(i));
    }
}
```

**输出:**

```cs
Key at index 2 is key3

```

**例 2:**

```cs
// C# code to get the key at
// the specified index of a
// SortedList object
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

        // storing the value of
        // index that needed by
        // used into a variable
        // it will throw an exception
        // as index is out of range of 
        // valid indexes of SortedList object
        int i = 7;

        // getting the key at index 7
        Console.WriteLine("Key at index {0} is {1}",
                          i, mylist.GetKey(i));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . getkey？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.getkey?view=netframework-4.7.2)