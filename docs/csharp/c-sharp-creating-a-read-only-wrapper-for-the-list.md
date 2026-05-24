# C# |为列表创建只读包装

> 原文:[https://www . geeksforgeeks . org/c-sharp-创建列表的只读包装器/](https://www.geeksforgeeks.org/c-sharp-creating-a-read-only-wrapper-for-the-list/)

**列表< T >。AsReadOnly 方法**用于获取当前集合的只读 ReadOnlyCollection < T >包装。

**语法:**

> 公共系统。collections . object model . readonlycollection as readonly()；

**返回值:**返回一个对象，该对象作为当前[列表< T >](https://www.geeksforgeeks.org/c-list-class/) 的只读包装。

**示例:**

```cs
// C# code to create a read-only
// wrapper for the List<T>
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);
        firstlist.Add(5);
        firstlist.Add(6);
        firstlist.Add(7);

        Console.WriteLine("Before Wrapping: ");

        // Displaying the elements in the List
        foreach(int i in firstlist)
        {
            Console.WriteLine(i);
        }

        // Creating a Read-Only packing
        // around the List<T>
        IList<int> mylist2 = firstlist.AsReadOnly();

        Console.WriteLine("After Wrapping: ");

        // Displaying the elements
        foreach(int m in mylist2)
        {
            Console.WriteLine(m);
        }

        Console.WriteLine("Trying to add new element into mylist2:");

        // it will give error
        mylist2.Add(8);
    }
}
```

**输出:**

```cs
Before Wrapping: 
1
2
3
4
5
6
7
After Wrapping: 
1
2
3
4
5
6
7
Trying to add new element into mylist2:

```

**运行时错误:**

> 未处理异常:
> 系统。NotSupportedException:集合是只读的。

**注:**

*   只读集合只是一个带有防止修改集合的包装的集合。如果对基础集合进行了更改，只读集合将反映这些更改。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . as readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.asreadonly?view=netframework-4.7.2)