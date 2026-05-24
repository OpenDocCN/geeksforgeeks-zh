# 在 C# 中列出 BinarySearch()方法

> 原文:[https://www . geesforgeks . org/list-binary search-method-in-c-sharp/](https://www.geeksforgeeks.org/list-binarysearch-method-in-c-sharp/)

列表<t>。BinarySearch()方法使用[二分搜索法算法](https://www.geeksforgeeks.org/binary-search/)来定位排序后的[列表<T>T4 中的特定元素或其一部分。此方法的重载列表中有 3 种方法，如下所示:](https://www.geeksforgeeks.org/c-list-class/)</t>

*   **双星搜索(T)**
*   **二元搜索(t，icmpar<t>)**
*   **BinarySearch(Int32，Int32，T，IComparer < T > )**

### 二进制搜索方法

此方法使用*默认比较器*在整个排序的 [**列表<>**](https://www.geeksforgeeks.org/c-list-class/)中搜索一个元素，并返回搜索到的元素的从零开始的索引。

**语法:**

```cs
public int BinarySearch (T item);
```

这里，项是要定位的对象，*项*的值可以是 ***空*** 或 ***引用*** 类型。

**返回类型:**如果找到了*项*，则该方法返回要搜索的元素的*从零开始的索引*，如果没有找到，则返回一个负数，即下一个元素的索引的*位*补码，该补码大于该项。如果没有更大的元素，将返回*计数*的*位*补码。

**异常:**如果默认比较器*默认*找不到 IComparable < T >泛型接口或 T 类型的 IComparable 接口的实现，此方法将给出***invalid operationexception***

以下程序说明了上述方法的使用:

**例 1:**

## C#

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

**Output:** 

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

**示例 2:** 在此示例中，列表是用一些整数值创建的，并使用用户定义函数在列表中使用 *BinarySearch(T)* 方法插入一个新的整数。

## C#

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

**Output:** 

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

### 二进制搜索方法

此方法使用指定的比较器在整个排序列表中搜索元素，并返回搜索到的元素的从零开始的索引。

**语法:**

> 公共二进制搜索(测试项目，系统。collections . generic . icomparer<t>comparer)；</t>

**参数:**

*   **项**:是需要定位的项，该项的值可以是*空*作为参照类型。
*   **比较器**:比较元素时使用的是 IComparer < T >实现。

**返回值:**如果找到了项，则该方法返回要搜索的元素的从零开始的索引，如果没有找到，则返回一个负数，该负数是大于项的下一个元素的索引的按位补数，或者，如果没有更大的元素，则返回 Count 的按位补数。

**异常:**如果比较器为空，并且默认的比较器 default 找不到类型为 *T* 的 IComparable < T >泛型接口或 IComparable 接口的实现，则此方法将给出*invalid operationexception*。

以下程序说明了上述方法的使用:

**例 1:**

## C#

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

**示例 2:** 在本例中，使用一些整数值创建列表，并使用用户定义的函数，使用 BinarySearch(T，Comparer < T >)方法在列表中插入一个新的整数。

## C#

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
5
6
1
9

List in sorted form
1
5
6
9

After inserting "3" in the List
1
3
5
6
9
```

### BinarySearch(Int32、Int32、t、icmpar<t>)</t>

此方法用于使用指定的比较器在排序列表<t>中的元素范围内搜索元素，并返回元素的从零开始的索引。</t>

**语法:**

> 公共整数二进制搜索(整数索引，整数计数，测试项目，系统。collections . generic . icomparer<t>comparer)；</t>

**参数:**

> **索引**:是要搜索范围的从零开始的索引。
> **计数**:是搜索范围的长度。
> **项**:是要定位的对象。对于引用类型，该值可以为 null。
> **比较器**:比较元素时使用的是 IComparer 实现，使用默认比较器 default 为 null。

**返回值:**如果找到项目，则返回排序列表< T >中项目的从零开始的索引；否则，返回一个负数，该负数是大于项的下一个元素的索引的按位补数，或者，如果没有更大的元素，则是 Count 的按位补数。

**异常:**

*   **argumentoutofrangerexception**:如果索引小于 0 或者计数小于 0。
*   **参数异常**:如果索引和计数不代表有效范围。
*   **无效操作异常**:如果比较器为空。

**示例:**

## C#

```cs
// C# program to demonstrate the
// List<T>.BinarySearch(Int32,
// Int32, T, Comparer <T>) method
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
15
4
2
9
5
7
6
8
10

Sort a range with the alternate comparer
15
2
4
5
6
7
8
9
10

BinarySearch a range and Insert 3
15
2
3
4
5
6
7
8
9
10
```

**注:**

*   如果列表<t>包含多个具有相同值的元素，则该方法只返回其中一个出现，并且它可能返回任何一个出现，不一定是第一个出现。</t>
*   列表<t>必须已经根据比较器实现进行了排序；否则，结果不正确。</t>
*   这个方法是一个 O(log n)运算，其中 n 是范围内的元素个数。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . binary search？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.binarysearch?view=netframework-4.7.2)