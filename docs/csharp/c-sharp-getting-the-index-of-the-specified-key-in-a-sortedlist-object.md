# C# |获取排序列表对象中指定键的索引

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-index-of-the-spected-key-in-a-sorted list-object/](https://www.geeksforgeeks.org/c-sharp-getting-the-index-of-the-specified-key-in-a-sortedlist-object/)

***排序列表。IndexOfKey(Object)方法*** 用于获取 SortedList 对象中指定键的从零开始的索引。

**语法:**

```cs
public virtual int IndexOfKey (object key);
```

这里，*键*是位于排序列表对象中的键。

**返回值:**如果在 SortedList 对象中找到键，则该方法返回键参数类型`System.Int32`的从零开始的索引，否则返回-1。

**异常:**

*   **ArgumentNullException** :如果密钥为空。
*   **无效操作异常**:如果比较器抛出异常。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get the zero-based index
// of the specified key in a SortedList
// object
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

        // printing the keys and values of mylist
        Console.WriteLine("Index \t\t Keys \t\tValues");

        for (int i = 0; i < mylist.Count; i++) 
        {
            Console.WriteLine("[{0}]\t\t{1}\t\t{2}", i,
                mylist.GetKey(i), mylist.GetByIndex(i));
        }

        Console.Write("\nThe index of key 'Third' is: "); 

        // getting the index of key "Third"
        Console.Write(mylist.IndexOfKey("Third"));

        // getting the index of key which is
        // not present in mylist so it will
        // return -1
        Console.Write("\nThe index of key 'Sixth' is: "); 
        Console.Write(mylist.IndexOfKey("Sixth"));
    }
}
```

**输出:**

```cs
Index          Keys         Values
[0]        Fifth        Manish
[1]        First        Ram
[2]        Fourth        Rohit
[3]        Second        Shyam
[4]        Third        Mohit

The index of key 'Third' is: 4
The index of key 'Sixth' is: -1

```

**例 2:** 演示`ArgumentNullException` 可能发生的情况

```cs
// C# code to get the zero-based index
// of the specified key in a SortedList
// object
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

        // printing the keys and values of mylist
        Console.WriteLine("Index \t\t Keys \t\tValues");

        for (int i = 0; i < mylist.Count; i++) 
        {
            Console.WriteLine("[{0}]\t\t{1}\t\t{2}", i,
                mylist.GetKey(i), mylist.GetByIndex(i));
        }

        Console.Write("\nThe index of key 'null' is: ");    

        // getting the index of key "null"
        // it will give ArgumentNullException
        Console.Write(mylist.IndexOfKey(null));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**注:**

*   索引序列基于排序序列。当一个元素被添加时，它会以正确的排序顺序被插入到 SortedList 中，索引也会相应地进行调整。当元素被移除时，索引也会相应地调整。因此，特定键/值对的索引可能会改变。
*   这个方法使用二分搜索法算法，所以这个方法是一个 O(log n)运算，其中 n 是计数。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . indexofkey？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.indexofkey?view=netframework-4.7.2)