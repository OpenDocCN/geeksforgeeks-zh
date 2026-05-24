# C# |替换排序列表对象中特定索引处的值

> 原文:[https://www . geeksforgeeks . org/c-sharp-替换特定索引中的值-sortedlist-object/](https://www.geeksforgeeks.org/c-sharp-replacing-the-value-at-a-specific-index-in-a-sortedlist-object/)

**排序列表。SetByIndex(Int32，Object)方法**用于替换 SortedList 对象中特定索引处的值。

**语法:**

```cs
public virtual void SetByIndex (int index, object value);
```

**参数:**

> **指标:**是指从零开始的指标，在这个指标上保存价值。
> 
> **值:**是保存到排序列表对象中的对象。该值可以是*空值*。

**异常:**如果索引超出给定排序列表对象的有效索引范围，此方法将抛出***argumentout of range Exception***。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code for replacing the value at a
// specific index in a SortedList object
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

        // Before replacing the keys
        // and values of SortedList are
        Console.WriteLine("----- Before Replacing -----");

        Console.WriteLine("Index \t\t Keys \t\tValues");

        for (int i = 0; i < mylist.Count; i++) {
            Console.WriteLine("[{0}]\t\t{1}\t\t{2}", i,
                              mylist.GetKey(i), mylist.GetByIndex(i));
        }

        Console.WriteLine();

        // After replacing the keys
        // and values of SortedList are
        Console.WriteLine("----- After Replacing -----");

        // Replaces the values at
        // index 1 and index 3.
        mylist.SetByIndex(1, "Priyanka");
        mylist.SetByIndex(3, "Ritu");

        Console.WriteLine("Index \t\t Keys \t\tValues");

        for (int i = 0; i < mylist.Count; i++) {
            Console.WriteLine("[{0}]\t\t{1}\t\t{2}", i,
                              mylist.GetKey(i), mylist.GetByIndex(i));
        }
    }
}
```

**输出:**

```cs
----- Before Replacing -----
Index          Keys         Values
[0]        Fifth        Manish
[1]        First        Ram
[2]        Fourth        Rohit
[3]        Second        Shyam
[4]        Third        Mohit

----- After Replacing -----
Index          Keys         Values
[0]        Fifth        Manish
[1]        First        Priyanka
[2]        Fourth        Rohit
[3]        Second        Ritu
[4]        Third        Mohit

```

**例 2:** 演示了*argumentout of range exception*可能发生的情况

```cs
// C# code giving ArgumentOutOfRangeException 
// specific index in a SortedList object
// but giving ArgumentOutOfRangeException 
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("h", "Hello"); 
        mylist.Add("g", "Geeks!"); 
        mylist.Add("w", "Welcome");
        mylist.Add("t", "to");
        mylist.Add("n", "Noida"); 

        // Before replacing the keys
        // and values of SortedList are
        Console.WriteLine("----- Before Replacing -----");

        Console.WriteLine("Index \t\t Keys \t\tValues");

        for (int i = 0; i < mylist.Count; i++) {
            Console.WriteLine("[{0}]\t\t{1}\t\t{2}", i,
                            mylist.GetKey(i), mylist.GetByIndex(i));
        }

        Console.WriteLine();

        // After replacing the keys
        // and values of SortedList are
        Console.WriteLine("----- After Replacing -----");

        // Replaces the values at
        // index 6 which is outside 
        // the range of valid indexes
        // here it will give an
        // ArgumentOutOfRangeException
        mylist.SetByIndex(6, null);

        Console.WriteLine("Index \t\t Keys \t\tValues");

        for (int i = 0; i < mylist.Count; i++) {
            Console.WriteLine("[{0}]\t\t{1}\t\t{2}", i,
                            mylist.GetKey(i), mylist.GetByIndex(i));
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**注:**

*   索引序列基于排序序列。当一个元素被添加时，它会以正确的排序顺序被插入到 SortedList 中，索引也会相应地进行调整。当元素被移除时，索引也会相应地调整。因此，在从 SortedList 对象中添加和移除元素后，特定键/值对的索引可能会改变。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . setby index？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.setbyindex?view=netframework-4.7.2)