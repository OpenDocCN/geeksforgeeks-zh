# C# |获取或设置集合

中指定索引处的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-or-set-the-element-at-specific-index-in-collection/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-element-at-specified-index-in-collectiont/)

**集合<T1**T>。Item[Int32] 属性用于获取或设置指定索引处的元素。

**语法:**

```cs
public T this[int index] { get; set; }

```

这里， ***索引*** 是要获取或设置的元素的从零开始的索引。

**返回值:**指定索引处的元素。

**异常:**如果*指数*小于零**或**指数等于**或**大于计数，此方法将给出**argumentout of range Exception**。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get or set the
// element at the specified index
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        // Adding elements in Collection myColl
        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // Displaying the elements in myColl
        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }

        // Get the element at index 2
        Console.WriteLine("Element at index 2 is : " + myColl[2]);

        // Get the element at index 3
        Console.WriteLine("Element at index 3 is : " + myColl[3]);

        // Set the element at index 3
        myColl[3] = "GFG";

        // Displaying the elements in myColl
        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
A
B
C
D
E
Element at index 2 is : C
Element at index 3 is : D
A
B
C
GFG
E

```

**例 2:**

```cs
// C# code to get or set the
// element at the specified index
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of ints
        Collection<int> myColl = new Collection<int>();

        // Adding elements in Collection myColl
        myColl.Add(2);
        myColl.Add(3);
        myColl.Add(4);
        myColl.Add(5);

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }

        // Get the element at index -1
        // This should raise "ArgumentOutOfRangeException"
        // as the index is less than 0
        Console.WriteLine("Element at index -1 is : " + myColl[-1]);

        // Set the element at index 2
        myColl[2] = 10;

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**注:**

*   集合< **T** >接受 null 作为引用类型的有效值，并允许重复元素。
*   此属性提供了使用语法访问集合中特定元素的能力: **myCollection[index]** 。
*   检索该属性的值是一个 O(1)操作。
*   设置属性也是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.item?view=netframework-4.7.2)