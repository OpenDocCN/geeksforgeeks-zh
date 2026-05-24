# C# |如何从列表的指定索引中删除元素

> 原文:[https://www . geesforgeks . org/c-sharp-如何从指定的列表索引中删除元素/](https://www.geeksforgeeks.org/c-sharp-how-to-remove-the-element-from-the-specified-index-of-the-list/)

**列表< T >。移除方法**用于移除列表< T >中指定索引处的元素。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果计数等于容量，则通过重新分配内部阵列，列表的容量会自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public void RemoveAt (int index);
```

**参数:**

> **索引:**是要删除的元素的从零开始的起始索引。
> **计数:**是要移除的元素数量。

**异常:**如果*指数*小于 0 或等于或大于 **[计数](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)** ，此方法将给出*argumentout of range exception*。

以下程序说明了**列表< T >的使用。移除 At (Int32)方法:**

**例 1:**

```cs
// C# Program to remove the element at
// the specified index of the List<T>
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(17);
        firstlist.Add(19);
        firstlist.Add(21);
        firstlist.Add(9);
        firstlist.Add(75);
        firstlist.Add(19);
        firstlist.Add(73);

        Console.WriteLine("Elements Present in List:\n");

        int p = 0;

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.Write("At Position {0}: ", p);
            Console.WriteLine(k);
            p++;
        }

        Console.WriteLine(" ");

        // removing the element at index 3
        Console.WriteLine("Removing the element at index 3\n");

        // 9 will remove from the List
        // and 75 will come at index 3
        firstlist.RemoveAt(3);

        int p1 = 0;

        // Displaying the elements of List
        foreach(int n in firstlist)
        {
            Console.Write("At Position {0}: ", p1);
            Console.WriteLine(n);
            p1++;
        }
    }
}
```

**输出:**

```cs
Elements Present in List:

At Position 0: 17
At Position 1: 19
At Position 2: 21
At Position 3: 9
At Position 4: 75
At Position 5: 19
At Position 6: 73

Removing the element at index 3

At Position 0: 17
At Position 1: 19
At Position 2: 21
At Position 3: 75
At Position 4: 19
At Position 5: 73

```

**例 2:**

```cs
// C# Program to remove the element at
// the specified index of the List<T>
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(17);
        firstlist.Add(19);
        firstlist.Add(21);
        firstlist.Add(9);
        firstlist.Add(75);
        firstlist.Add(19);
        firstlist.Add(73);

        Console.WriteLine("Elements Present in List:\n");

        int p = 0;

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.Write("At Position {0}: ", p);
            Console.WriteLine(k);
            p++;
        }

        Console.WriteLine(" ");

        // removing the element at index 3
        Console.WriteLine("Removing the element at index 3\n");

        // taking negative index
        // it will give error as index
        // cannot be less than 0
        firstlist.RemoveAt(-1);

        int p1 = 0;

        // Displaying the elements of List
        foreach(int n in firstlist)
        {
            Console.Write("At Position {0}: ", p1);
            Console.WriteLine(n);
            p1++;
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**输出:**

```cs
Elements Present in List:

At Position 0: 17
At Position 1: 19
At Position 2: 21
At Position 3: 9
At Position 4: 75
At Position 5: 19
At Position 6: 73

Removing the element at index 3

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . remove at？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.removeat?view=netframework-4.7.2)