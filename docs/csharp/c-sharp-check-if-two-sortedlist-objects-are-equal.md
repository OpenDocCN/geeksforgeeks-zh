# C# |检查两个排序列表对象是否相等

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-two-sorted list-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-sortedlist-objects-are-equal/)

从对象类继承的**等于(对象)方法**用于检查指定的[排序列表](https://www.geeksforgeeks.org/c-sortedlist-class/)对象是否等于另一个排序列表对象。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to if a SortedList
// is equal to another SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a sorted list of key/value pairs
        SortedList fslist = new SortedList();

        // Adding pairs to fslist
        fslist.Add("Maths ", 98);
        fslist.Add("English ", 99);
        fslist.Add("Physics ", 97);
        fslist.Add("Chemistry", 96);
        fslist.Add("CSE     ", 100);

        // Checking whether fslist is
        // equal to itself or not
        Console.WriteLine(fslist.Equals(fslist));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# program to if a SortedList
// is equal to another SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a sorted list of key/value pairs
        SortedList fslist = new SortedList();

        // Adding pairs to fslist
        fslist.Add("Maths ", 98);
        fslist.Add("English ", 99);
        fslist.Add("Physics ", 97);
        fslist.Add("Chemistry", 96);
        fslist.Add("CSE     ", 100);

        // Creating an SortedList
        SortedList fslist2 = new SortedList();

        // Adding elements to SortedList
        fslist2.Add("1", "one");
        fslist2.Add("2", "two");
        fslist2.Add("3", "three");
        fslist2.Add("4", "four");
        fslist2.Add("5", "five");

        // Checking whether fslist is
        // equal to fslist2 or not
        Console.WriteLine(fslist.Equals(fslist2));

        // Creating a sorted list of key/value pairs
        SortedList fslist3 = new SortedList();

        // Assigning fslist2 to fslist3
        fslist3 = fslist2;

        // Checking whether fslist3 is
        // equal to fslist2 or not
        Console.WriteLine(fslist3.Equals(fslist2));    
    }
}
```

**输出:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。