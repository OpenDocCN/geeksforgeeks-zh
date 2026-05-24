# C# |如何将集合的元素插入列表中指定的索引处

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何将集合中的元素插入指定索引处的列表/](https://www.geeksforgeeks.org/c-sharp-how-to-insert-the-elements-of-a-collection-into-the-list-at-the-specified-index/)

**列表< T >。InsertRange(Int32，IEnumerable < T >)方法**用于将集合的元素插入列表< T >中指定的索引处。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果计数等于容量，则通过重新分配内部阵列，列表的容量会自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public void InsertRange (int index, System.Collections.Generic.IEnumerable<T> collection);

```

**参数:**

> **索引:**是应该插入新元素的从零开始的索引。
> 
> **集合:**是其元素将被插入列表< T >的集合

**注意:**集合本身不能为空。但是如果类型 T 是引用类型，它可以包含可以为空的元素。

**异常:**

*   **ArgumentNullException:** 如果集合为空。
*   **argumentoutofrangerexception:**如果索引小于零或大于计数。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# Program to insert the elements of
// a collection into the List<T> at the
// specified index
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        string[] str1 = { "Geeks",
                          "for",
                          "Geeks" };

        // Creating an List<T> of strings
        // adding str1 elements to List
        List<String> firstlist = new List<String>(str1);

        // displaying the elements of firstlist
        Console.WriteLine("Elements in List: \n");

        foreach(string dis in firstlist)
        {
            Console.WriteLine(dis);
        }

        Console.WriteLine(" ");

        // contains new Elements which is
        // to be added in the List
        str1 = new string[] { "New",
                              "Element",
                              "Added" };

        // using InsertRange Method
        Console.WriteLine("InsertRange(2, str1)\n");

        // adding elements after 2nd
        // index of the List
        firstlist.InsertRange(2, str1);

        // displaying the elements of
        // List after InsertRange Method
        foreach(string res in firstlist)
        {
            Console.WriteLine(res);
        }
    }
}
```

**输出:**

```cs
Elements in List: 

Geeks
for
Geeks

InsertRange(2, str1)

Geeks
for
New
Element
Added
Geeks

```

**例 2:**

```cs
// C# Program to insert the elements of
// a collection into the List<T> at the
// specified index
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        string[] str1 = { "Geeks",
                          "for",
                          "Geeks" };

        // Creating an List<T> of strings
        // adding str1 elements to List
        List<String> firstlist = new List<String>(str1);

        // displaying the elements of firstlist
        Console.WriteLine("Elements in List: \n");

        foreach(string dis in firstlist)
        {
            Console.WriteLine(dis);
        }

        Console.WriteLine(" ");

        // contains new Elements which is
        // to be added in the List
        str1 = new string[] { "New",
                              "Element",
                              "Added" };

        // using InsertRange Method
        Console.WriteLine("InsertRange(2, str1)\n");

        // this will give error as
        // index is less than 0
        firstlist.InsertRange(-1, str1);

        // displaying the elements of
        // List after InsertRange Method
        foreach(string res in firstlist)
        {
            Console.WriteLine(res);
        }
    }
}
```

**错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . insert range？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.insertrange?view=netframework-4.7.2)