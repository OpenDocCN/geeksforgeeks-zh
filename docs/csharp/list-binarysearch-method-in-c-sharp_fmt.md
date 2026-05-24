# 在 C# 中列出 BinarySearch()方法

> 原文: [https://www.geeksforgeeks.org/list-binarysearch-method-in-c-sharp/](https://www.geeksforgeeks.org/list-binarysearch-method-in-c-sharp/)

`List<T>.BinarySearch()`方法使用[二分搜索法算法](https://www.geeksforgeeks.org/binary-search/)来定位排序后的[`List<T>`](https://www.geeksforgeeks.org/c-list-class/)中的特定元素或其一部分。此方法的重载列表中有 3 种方法，如下所示：

## BinarySearch()方法的重载形式

*   `BinarySearch(T)`
*   `BinarySearch(T, IComparer<T>)`
*   `BinarySearch(Int32, Int32, T, IComparer<T>)`

### BinarySearch(T)方法

此方法使用*默认比较器*在整个排序的[`List<T>`](https://www.geeksforgeeks.org/c-list-class/)中搜索一个元素，并返回搜索到的元素的从零开始的索引。

**语法:**

```cs
public int BinarySearch (T item);
```

这里，`item`是要定位的对象，`item`的值可以是`null`或引用类型。

**返回类型:** 如果找到了`item`，则该方法返回要搜索的元素的从零开始的索引，如果没有找到，则返回一个负数，即下一个元素的索引的按位补码，该补码大于该项。如果没有更大的元素，将返回`Count`的按位补码。

**异常:** 如果默认比较器`default`找不到`IComparable<T>`泛型接口或`T`类型的`IComparable`接口的实现，此方法将给出`InvalidOperationException`。

以下程序说明了上述方法的使用：

**例 1:**

```cs
// C# program to illustrate the
// List<T>.BinarySearch(T) Method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {
        // List creation
        List<string> Geek = new List<string>();

        // List elements
        Geek.Add("ABCD");
        Geek.Add("QRST");
        Geek.Add("XYZ");
        Geek.Add("IJKL");

        Console.WriteLine("The Original List is:");
        foreach(string g in Geek)
        {
            // prints original List
            Console.WriteLine(g);
        }

        Console.WriteLine("\nThe List in Sorted form");

        // sort the List
        Geek.Sort();

        Console.WriteLine();
        foreach(string g in Geek)
        {
            // prints the sorted List
            Console.WriteLine(g);
        }

        Console.WriteLine("\nInsert EFGH :");

        // insert "EFGH" in the List
        //"EFGH" insert into its original
        // position when the List is sorted
        int index = Geek.BinarySearch("EFGH");

        if (index < 0)
        {
            Geek.Insert(~index, "EFGH");
        }

        Console.WriteLine();

        foreach(string g in Geek)
        {
            // prints the sorted list
            // after inserting "EFGH"
            Console.WriteLine(g);
        }
    }
}
```

**输出:**

```cs
The Original List is:
ABCD
QRST
XYZ
IJKL

The List in Sorted form

ABCD
IJKL
QRST
XYZ

Insert EFGH :

ABCD
EFGH
IJKL
QRST
XYZ
```

**示例 2:** 在此示例中，列表是用一些整数值创建的，并使用用户定义函数在列表中使用`BinarySearch(T)`方法插入一个新的整数。

```cs
// C# program to illustrate the
// List<T>.BinarySearch(T) Method
using System;
using System.Collections.Generic;

class GFG {

    // method for inserting "3"
    public void binarySearch(List<int> Geek)
    {
        // insert "3" in the List
        Console.WriteLine("\nInsert 3 :");

        // "3" insert into its original
        // position when the List is
        // sorted
        int index = Geek.BinarySearch(3);

        if (index < 0)
        {
            Geek.Insert(~index, 3);
        }

        foreach(int g in Geek)
        {
            // prints the sorted list
            // after inserting "3"
            Console.WriteLine(g);
        }
    }
}

// Driver Class
public class search {

    public static void Main()
    {
        // List creation
        GFG gg = new GFG();

        List<int> Geek = new List<int>() {
                              5, 6, 1, 9};

        Console.WriteLine("Original List");

        foreach(int g in Geek)
        {
            Console.WriteLine(g);
            // prints original List
        }

        Console.WriteLine("\nList in Sorted form");
        Geek.Sort();

        foreach(int g in Geek)
        {
            Console.WriteLine(g);
            // prints the sorted List
        }

        // calling the method "binarySearch"
        gg.binarySearch(Geek);
    }
}
```

**输出:**

```cs
Original List
5
6
1
9

List in Sorted form
1
5
6
9

Insert 3 :
1
3
5
6
9
```

### BinarySearch(T, IComparer<T>)方法

此方法使用指定的比较器在整个排序列表中搜索元素，并返回搜索到的元素的从零开始的索引。

**语法:**

```cs
public int BinarySearch (T item, System.Collections.Generic.IComparer<T> comparer);
```

**参数:**

*   `item`: 是需要定位的项，该项的值可以是`null`作为引用类型。
*   `comparer`: 比较元素时使用的是`IComparer<T>`实现。

**返回值:** 如果找到了`item`，则该方法返回要搜索的元素的从零开始的索引，如果没有找到，则返回一个负数，该负数是大于`item`的下一个元素的索引的按位补数，或者，如果没有更大的元素，则返回`Count`的按位补数。

**异常:** 如果`comparer`为`null`，并且默认的比较器`default`找不到类型为`T`的`IComparable<T>`泛型接口或`IComparable`接口的实现，则此方法将给出`InvalidOperationException`。

以下程序说明了上述方法的使用：

**例 1:**

```cs
// C# program to demonstrate the
// List<T>.BinarySearch(T,
// IComparer<T>) Method
using System;
using System.Collections.Generic;

class GFG : IComparer<string> {

    public int Compare(string x, string y)
    {
        if (x == null || y == null)
        {
            return 0;
        }
        return x.CompareTo(y);
        //"CompareTo()" method
    }
}

// Driver Class
class geek {

    // Main Method
    public static void Main()
    {
        // list creation
        List<string> list1 = new List<string>();

        // list elements
        list1.Add("B");
        list1.Add("C");
        list1.Add("E");
        list1.Add("A");

        // prints Original list
        Console.WriteLine("Original string");

        foreach(string g in list1)
        {
            Console.WriteLine(g);
        }

        GFG gg = new GFG();

         // sort the list
        list1.Sort(gg);

        // prints the sorted form of original list
        Console.WriteLine("\nList in sorted form");

        foreach(string g in list1)
        {
            Console.WriteLine(g);
        }

        //"D" is going to insert
        //"gg" is the IComparer
        int index = list1.BinarySearch("D", gg);

        if (index < 0)
        {
            list1.Insert(~index, "D");
        }

        // prints the final List
        Console.WriteLine("\nAfter inserting \"D\" in the List");

        foreach(string g in list1)
        {
            Console.WriteLine(g);
        }
    }
}
```

**输出:**

```cs
Original string
B
C
E
A

List in sorted form
A
B
C
E

After inserting "D" in the List
A
B
C
D
E
```

**示例 2:** 在本例中，使用一些整数值创建列表，并使用用户定义的函数，使用`BinarySearch(T, IComparer<T>)`方法在列表中插入一个新的整数。

# C#

```cs
// C# program to demonstrate the
// List<T>.BinarySearch(T,
// IComparer<T>) Method
using System;
using System.Collections.Generic;

class GFG : IComparer<int> {

    public int Compare(int x, int y)
    {
        if (x == 0 || y == 0)
        {
            return 0;
        }
        return x.CompareTo(y);
    }
}

// Driver Class
class geek {

    // Main Method
    public static void Main()
    {
        // list creation
        List<int> list1 = new List<int>() {
                               5, 6, 1, 9};

        // prints Original list
        Console.WriteLine("Original string");

        foreach(int g in list1)
        {
            Console.WriteLine(g);
        }

         // creating object of class GFG
        GFG gg = new GFG();

        // sort the list
        list1.Sort(gg);

        // prints the sorted form
        // of original list
        Console.WriteLine("\nList in sorted form");

        foreach(int g in list1)
        {
            Console.WriteLine(g);
        }

        bSearch b = new bSearch();
        b.binarySearch(list1);
    }
}

class bSearch {

    public void binarySearch(List<int> list1)
    {

        // creating object of class GFG
        GFG gg = new GFG();

        // "3" is going to insert
        // "gg" is the IComparer
        int index = list1.BinarySearch(3, gg);

        if (index < 0)
        {
            list1.Insert(~index, 3);
        }

        // prints the final List
        Console.WriteLine("\nAfter inserting \"3\" in the List");
        foreach(int g in list1)
        {
            Console.WriteLine(g);
        }
    }
}
```

**Output:**

```cs
Original string

List in sorted form

After inserting "3" in the List
```

## BinarySearch(Int32, Int32, T, IComparer<T>)

此方法用于使用指定的比较器在排序列表`<T>`中的元素范围内搜索元素，并返回元素的从零开始的索引。

**语法:**

> `public int BinarySearch(int index, int count, T item, System.Collections.Generic.IComparer<T> comparer);`

**参数:**

> `index`: 是要搜索范围的从零开始的索引。
> `count`: 是搜索范围的长度。
> `item`: 是要定位的对象。对于引用类型，该值可以为 `null`。
> `comparer`: 比较元素时使用的是 `IComparer<T>` 实现，使用默认比较器 `default` 为 `null`。

**返回值:** 如果找到项目，则返回排序列表`<T>`中项目的从零开始的索引；否则，返回一个负数，该负数是大于 `item` 的下一个元素的索引的按位补数，或者，如果没有更大的元素，则是 `Count` 的按位补数。

**异常:**

*   `ArgumentOutOfRangeException`: 如果 `index` 小于 0 或者 `count` 小于 0。
*   `ArgumentException`: 如果 `index` 和 `count` 不代表有效范围。
*   `InvalidOperationException`: 如果 `comparer` 为空。

**示例:**

# C#

```cs
// C# program to demonstrate the
// List<T>.BinarySearch(Int32,
// Int32, T, Comparer<T>) method
using System;
using System.Collections.Generic;

class GFG : IComparer<int>
{
    public int Compare(int x, int y)
    {
        if (x == 0 || y == 0)
        {
            return 0;
        }
        return x.CompareTo(y);
    }
}

class search {

    // "binarySearch" function
    public void binarySearch(List<int> list1,
                                  int i)
    {
        Console.WriteLine("\nBinarySearch a "+
                       "range and Insert 3");

        // "gg" is the object of class GFG
        GFG gg = new GFG();

        // binary search
        int index = list1.BinarySearch(0, i,
                                     3, gg);

        if (index < 0)
        {

            // insert "3"
            list1.Insert(~index, 3);
            i++;
        }

        Display(list1);
    }

    // "Display" function
    public void Display(List<int> list)
    {

        foreach( int g in list )
        {
            Console.WriteLine(g);
        }
    }
}

// Driver Class
class geek
{

    // Main Method
    public static void Main()
    {
        List<int> list1 = new List<int>()
        {
            // list elements
            15,4,2,9,5,7,6,8,10

        };

        int i = 7;
        Console.WriteLine("Original List");

        // "d" is the object of
        // the class "search"
        search d = new search();

        // prints Original list
        d.Display(list1);

        // "gg" is the object
        // of class GFG
        GFG gg = new GFG();

        Console.WriteLine("\nSort a range with "+
                       "the alternate comparer");

        // sort is happens between
        // index 1 to 7           
        list1.Sort(1, i, gg);

        // prints sorted list
        d.Display(list1);

        // call "binarySearch" function
        d.binarySearch(list1,i);

    }
}
```

**Output:**

```cs
Original List

Sort a range with the alternate comparer

BinarySearch a range and Insert 3
```

**注:**

*   如果列表`<T>`包含多个具有相同值的元素，则该方法只返回其中一个出现，并且它可能返回任何一个出现，不一定是第一个出现。
*   列表`<T>`必须已经根据比较器实现进行了排序；否则，结果不正确。
*   这个方法是一个 `O(log n)` 运算，其中 `n` 是范围内的元素个数。

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.binarysearch?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.binarysearch?view=netframework-4.7.2)