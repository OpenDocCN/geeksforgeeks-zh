# 如何在 C# | List 中对列表进行排序。排序()方法集-1

> 原文:[https://www . geesforgeks . org/how-to-sort-list-in-c-sharp-set-1/](https://www.geeksforgeeks.org/how-to-sort-list-in-c-sharp-set-1/)

**列表< T >。Sort()方法**用于使用指定的或默认的 IComparer < T >实现或提供的比较< T >委托来比较列表元素，对列表< T >中的元素或部分元素进行排序。该方法的重载列表中总共有 4 种方法，如下所示:

2.  **[排序(IComparer < T > )](# m1)**
3.  **[排序(Int32，Int32，IComparer <t>)</t>](# m2)**
4.  **排序()**
5.  **排序(比较<t>)</t>**

**在这里，我们将讨论前两种方法。**

##### **排序(IComparer < T >)方法**

**该方法用于使用指定的比较器对整个列表<t>中的元素进行排序。</t>**

****语法:****

```cs
public void Sort (System.Collections.Generic.IComparer<T> comparer);
```

**这里，比较器是比较元素时使用的 IComparer <t>实现，或者使用默认比较器 default 为 null。</t>**

****异常:****

*   ****invalid operationexception:**如果比较器为空，并且默认比较器 default 找不到类型为 T 的 IComparable < T >泛型接口或 IComparable 接口的实现**
*   ****ArgumentException:** 如果比较器的实现在排序过程中导致错误。例如，当比较一个项目和它自己时，比较器可能不会返回 0。**

****例 1:****

```cs
// C# program to demonstrate the concept of 
// List<T>.Sort(IComparer <T>) method
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

        // CompareTo() method
        return x.CompareTo(y);

    }
}

public class geek
{

    // Main Method
    public static void Main()
    {

        // List initialize
        List<int> list1 = new List<int>
        {

            // list elements
            1,5,6,2,4,3

        };

        Console.WriteLine("Original List");

        foreach(int g in list1)
        {

            // Display Original List
            Console.WriteLine(g);

        }

        // "gg" is the object oif class GFG
        GFG gg = new GFG();

        Console.WriteLine("\nSort with a comparer:");

        // use of List<T>.Sort(IComparer<T>) 
        // method. The comparer is "gg"
        list1.Sort(gg);

        foreach( int g in list1 )
        {

            // Display sorted list
            Console.WriteLine(g);

        }
    }
}
```

****Output:**

```cs
Original List
1
5
6
2
4
3

Sort with a comparer:
1
2
3
4
5
6

```** 

****例 2:****

```cs
// C# program to demonstrate the concept of 
// List<T>.Sort(IComparer <T>) method
using System;
using System.Collections.Generic;

class GFG : IComparer<string>
{
    public int Compare(string x, string y)
    {

        if (x == null || y == null)
        {
            return 0;
        }

        // "CompareTo()" method
        return x.CompareTo(y);

    }
}

public class geek
{

    // Main Method
    public static void Main()
    {
        List<string> list1 = new List<string>();

        // list elements
        list1.Add("A");
        list1.Add("I");
        list1.Add("G");
        list1.Add("B");
        list1.Add("E");
        list1.Add("H");
        list1.Add("F");
        list1.Add("C");
        list1.Add("J");

        Console.WriteLine("Original List");

        // Display Original List
        Display(list1);

        // "gg" is the object
        GFG gg = new GFG();

        Console.WriteLine("\nSort with a comparer:");

        // sort the list with a 
        // specified comparer "gg"
        list1.Sort(gg);

        // Display sorted List
        Display(list1);

        Console.WriteLine("\nBinarySearch and Insert D");

        // Binary Search for "D"
        // using List.BinarySearch(T) method
        int index = list1.BinarySearch("D");

        if (index < 0)
        {

            // range++;
            list1.Insert(~index, "D");

        }

        // Display the List after
        // inserting "D"
        Display(list1);

    }

    // Display function
    public static void Display(List<string> list)
    {
        foreach( string g in list )
        {
            Console.WriteLine(g);
        }
    }
}
```

****Output:**

```cs
Original List
A
I
G
B
E
H
F
C
J

Sort with a comparer:
A
B
C
E
F
G
H
I
J

BinarySearch and Insert D
A
B
C
D
E
F
G
H
I
J

```** 

##### **列表< T >。排序(Int32，Int32，IComparer < T >)方法**

**此方法用于使用指定的比较器对列表<t>中的元素范围内的元素进行排序。</t>**

****语法:****

```cs
public void Sort(int index, int len, IComparer<T> comparer)
```

****参数:****

> ****索引**:是排序将要发生的范围的从零开始的索引。**
> 
> ****len** :是范围的长度。**
> 
> ****比较器**:当比较元素时，使用*比较器*实现，或者为空，使用默认的比较器 default。**

****异常:****

*   ****argumentout of range exception**:如果*指数*或 *len* 小于 0。**
*   ****参数异常**:如果*索引*和计数没有在*列表*中指定有效范围。**
*   **无效操作抑制:如果*比较*为 null。**

****示例:****

```cs
// C# program to demonstrate the use of 
// List<T>.Sort(Int32, Int32, IComparer<T>)
// Method
using System;
using System.Collections.Generic;

class GFG : IComparer<string>
{
    public int Compare(string x, string y)
    {
        if (x == null || y == null)
        {
            return 0;
        }

        // "CompareTo()" method
        return x.CompareTo(y);

    }
}

public class geek
{
    public static void Main()
    {
        List<string> list1 = new List<string>();

        // list elements
        list1.Add("C++");
        list1.Add("Java");
        list1.Add("C");
        list1.Add("Python");
        list1.Add("HTML");
        list1.Add("CSS");
        list1.Add("Scala");
        list1.Add("Ruby");
        list1.Add("Perl");

        int range = 4;
        Console.WriteLine("Original List");

        // Display Original List
        Display(list1);

        // "gg" is the object
        GFG gg = new GFG();

        Console.WriteLine("\nSort a range with comparer:");

        // sort the list within a 
        // range of index 1 to 4
        // where range = 4
        list1.Sort(1, range, gg);

        // Display sorted List
        Display(list1);

        Console.WriteLine("\nBinarySearch and Insert Dart");

        // Binary Search and storing 
        // index value to "index"
        int index = list1.BinarySearch(0, range,
                                    "Dart", gg);

        if (index < 0)
        {
            list1.Insert(~index, "Dart");
            range++;
        }

        // Display the List 
        // after inserting "Dart"
        Display(list1);

    }

    // Display function
    public static void Display(List<string> list)
    {
        foreach(string g in list)
        {
            Console.WriteLine(g);
        }
    }
}
```

****Output:**

```cs
Original List
C++
Java
C
Python
HTML
CSS
Scala
Ruby
Perl

Sort a range with comparer:
C++
C
HTML
Java
Python
CSS
Scala
Ruby
Perl

BinarySearch and Insert Dart
C++
C
Dart
HTML
Java
Python
CSS
Scala
Ruby
Perl

```** 

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . sort？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.sort?view=netframework-4.7.2)**