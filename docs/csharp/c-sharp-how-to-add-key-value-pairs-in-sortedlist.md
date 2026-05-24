# C# |如何在 SortedList

中添加键/值对

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何添加键值对-in-sortedlist/](https://www.geeksforgeeks.org/c-sharp-how-to-add-key-value-pairs-in-sortedlist/)

SortedList 类是按键排序的**(键，值)对**的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于*T3 系统。收藏*命名空间。**排序列表。Add(Object，Object)方法**用于向 SortedList 对象添加具有指定键和值的元素。

**排序列表的属性:**

*   在内部，SortedList 的对象维护两个数组。第一个数组用于存储列表中的元素，即键，第二个数组用于存储相关的值。
*   键不能为空，但值可以为空。
*   As SortedList 使用了排序，这使得它比 Hashtable 慢。
*   排序列表的容量可以通过重新分配来动态增加。
*   排序列表中的键不能重复，但值可以重复。
*   排序列表可以使用 IComparer(升序或降序)根据关键字进行排序。

**语法:**

```cs
public virtual void Add (object key, object value);

```

**参数:**

> **键:**是要添加的元素的键。
> 
> **值:**是待加元素的值。该值可以为空。

**异常:**

*   **ArgumentNullException:** 如果密钥为空。
*   **ArgumentException:** 如果具有指定键的元素已经存在于 SortedList 对象中，或者 SortedList 被设置为使用 IComparable 接口，并且该键没有实现 IComparable 接口。
*   **notSupportDexception:**如果 SortedList 是只读的或具有固定大小。
*   **OutOfMemoryException:** 如果系统中没有足够的可用内存将这些对添加到排序列表中。
*   **无效操作异常:**如果比较器抛出异常。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate how to add key/value
// pair in SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a sorted list of key/value pairs
        SortedList fslist = new SortedList();

        // Adding pairs to fslist
        fslist.Add("Maths    ", 98);
        fslist.Add("English  ", 99);
        fslist.Add("Physics  ", 97);
        fslist.Add("Chemistry", 96);
        fslist.Add("CSE      ", 100);

        // Displays the marks in different
        // subjects sorted according to keys
        // i.e subjects
        // Here Count property is used to count
        // the total number of pairs in SortedList
        for (int i = 0; i < fslist.Count; i++) {
            Console.WriteLine("{0}:\t{1}", fslist.GetKey(i),
                                      fslist.GetByIndex(i));
        }
    }
}
```

**输出:**

```cs
Chemistry:    96
CSE      :    100
English  :    99
Maths    :    98
Physics  :    97

```

**例 2:**

```cs
// C# program to illustrate how to add
// key/value pair in SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a sorted list of key/value pairs
        SortedList fslist = new SortedList();

        // Adding pairs to fslist
        fslist.Add("Maths    ", 98);
        fslist.Add("English  ", 99);
        fslist.Add("Physics  ", 97);
        fslist.Add("Chemistry", 96);

        // this will give error as we are
        // adding duplicate key i.e Chemistry
        fslist.Add("Chemistry", 100);
    }
}
```

**错误:**

> 未处理异常:
> 系统。参数异常:项目已经添加。字典中的键:“化学”键正在添加:“化学”
> 在系统中。集合。对象键，系统。对象值)在:0【极客的 T2】。主(系统。0 中的字符串[]参数)

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.add?view=netframework-4.7.2)