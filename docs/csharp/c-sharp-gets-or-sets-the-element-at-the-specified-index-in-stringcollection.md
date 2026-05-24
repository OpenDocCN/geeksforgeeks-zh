# C# |获取或设置 StringCollection 中指定索引处的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-or-set-the-element-at-specific-index-in-string collection/](https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-element-at-the-specified-index-in-stringcollection/)

***StringCollection。项目[Int32]属性*** 用于获取或设置指定索引处的元素。

**语法:**

```cs
public string this[int index] { get; set; }
```

这里，*索引*是要获取或设置的条目的从零开始的索引。

**返回值:**返回指定索引处的*字符串*类型的元素。

**异常:**如果*指数*小于零或*指数*等于或大于[计数](https://www.geeksforgeeks.org/c-get-the-number-of-strings-in-stringcollection/)，则该属性抛出`ArgumentOutOfRangeException`。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to get or set the element at
// the specified index in StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("A");
        myCol.Add("B");
        myCol.Add("C");
        myCol.Add("D");
        myCol.Add("E");

        // Displaying objects in myCol
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }

        Console.WriteLine("\nAfter Item[int32] Property: \n");

        // setting the value at index 2
        myCol[2] = "Z";

        // Displaying the elements
        // in the StringCollection
        foreach(Object obj1 in myCol)
        {
            Console.WriteLine(obj1);
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

After Item[int32] Property: 

A
B
Z
D
E

```

**例 2:**

```cs
// C# code to get or set the element at
// the specified index in StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("Geeks");
        myCol.Add("GFG");
        myCol.Add("DS");
        myCol.Add("Class");
        myCol.Add("Noida");

        // Displaying objects in myCol
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }

        Console.WriteLine("\nAfter Item[int32] Property: \n");

        // setting the value at index 8
        // this will give error as index
        // is greater than count
        myCol[8] = "C#";

        // Displaying the elements
        // in the StringCollection
        foreach(Object obj1 in myCol)
        {
            Console.WriteLine(obj1);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.item?view=netframework-4.7.2)