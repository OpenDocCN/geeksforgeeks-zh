# C# |将容量设置为排序列表对象中的实际元素数量

> 原文:[https://www . geeksforgeeks . org/c-sharp-将容量设置为排序列表中元素的实际数量/](https://www.geeksforgeeks.org/c-sharp-setting-the-capacity-to-the-actual-number-of-elements-in-a-sortedlist-object/)

***排序列表。TrimToSize 方法*** 用于将容量设置为 SortedList 对象中元素的实际数量。
**语法:**

```cs
public virtual void TrimToSize ();
```

**异常:**如果 SortedList 对象为[只读](https://www.geeksforgeeks.org/c-check-if-a-sortedlist-is-read-only/)或者 SortedList 具有[固定大小](https://www.geeksforgeeks.org/c-check-if-a-sortedlist-object-has-a-fixed-size/)，此方法将抛出*notsupportdexception*。
以下程序说明了上述方法的使用:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// SortedList.TrimToSize() Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // create and initialize new SortedList
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("1", "C++");
        mylist.Add("2", "Java");
        mylist.Add("3", "DSA");
        mylist.Add("4", "Python");
        mylist.Add("5", "C#");
        mylist.Add("6", "HTML");

        // Capacity of SortedList before trimmimg
        Console.WriteLine("Before trimming the capacity is: {0}",
                                                mylist.Capacity);

        // trim the SortedList
        mylist.TrimToSize();

        // Capacity of ArrayList after trimming
        Console.WriteLine("After trimming the capacity is: {0}",
                                               mylist.Capacity);
    }
}
```

**Output:** 

```cs
Before trimming the capacity is: 16
After trimming the capacity is: 6
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// SortedList.TrimToSize() Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {

        // create and initialize new SortedList
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("h", "Hello");
        mylist.Add("g", "Geeks!");
        mylist.Add("w", "Welcome");
        mylist.Add("t", "to");
        mylist.Add("n", "Noida");

        // Displaying the count, capacity
        // and values of the SortedList.
        Console.WriteLine("Before Using TrimToSize Method:");
        Console.WriteLine();
        Console.WriteLine("Count: {0}", mylist.Count);
        Console.WriteLine("Capacity: {0}", mylist.Capacity);
        Console.Write("Values are: ");
        Display(mylist);

        Console.WriteLine();

        // Trim the SortedList.
        mylist.TrimToSize();

        // Displaying the count, capacity
        // and values of the SortedList.
        Console.WriteLine();
        Console.WriteLine("After Using TrimToSize Method:");
        Console.WriteLine();
        Console.WriteLine("Count: {0}", mylist.Count);
        Console.WriteLine("Capacity: {0}", mylist.Capacity);
        Console.Write("Values are: ");
        Display(mylist);

        // Clear the SortedList
        mylist.Clear();

        Console.WriteLine();

        // Displaying the count, capacity
        // and values of the SortedList.
        Console.WriteLine();
        Console.WriteLine("After Using Clear Method:");
        Console.WriteLine();
        Console.WriteLine("Count: {0}", mylist.Count);
        Console.WriteLine("Capacity: {0}", mylist.Capacity);
        Console.Write("Values are: ");
        Display(mylist);

        // again trim the SortedList
        mylist.TrimToSize();

        Console.WriteLine();

        // Displaying the count, capacity
        // and values of the SortedList.
        Console.WriteLine();
        Console.WriteLine("After Again Using TrimToSize Method:");
        Console.WriteLine();
        Console.WriteLine("Count: {0}", mylist.Count);
        Console.WriteLine("Capacity: {0}", mylist.Capacity);
        Console.Write("Values are: ");
        Display(mylist);
    }

    // to display the values of SortedList
    public static void Display(SortedList mylist)
    {
        // taking an IList and
        // using GetValueList method
        IList vlist = mylist.GetValueList();

        for (int i = 0; i < mylist.Count; i++)
            Console.Write(vlist[i] + " ");
    }
}
```

**Output:** 

```cs
Before Using TrimToSize Method:

Count: 5
Capacity: 16
Values are: Geeks! Hello Noida to Welcome 

After Using TrimToSize Method:

Count: 5
Capacity: 5
Values are: Geeks! Hello Noida to Welcome 

After Using Clear Method:

Count: 0
Capacity: 5
Values are: 

After Again Using TrimToSize Method:

Count: 0
Capacity: 0
Values are:
```