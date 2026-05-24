# C# |删除集合指定索引处的元素

> 原文:[https://www . geesforgeks . org/c-sharp-remove-element-at-specified-index-of-collection/](https://www.geeksforgeeks.org/c-sharp-remove-element-at-specified-index-of-collectiont/)

**收藏<T1**T>。RemoveAt(Int32) 用于移除集合< **T** >中指定索引处的元素。

**语法:**

```cs
public void RemoveAt (int index);

```

这里， ****索引**** 是要移除的元素的从零开始的索引。

**异常:**如果*指标*小于零*T9】或 T11*指标*等于或大于 Count，此方法将给出*T3【argumentout of range Exception】T5。**

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the element
// at the specified index of the Collection
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

        // To print the count of elements in Collection
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }

        // Removing the element at the
        // specified index of the Collection
        myColl.RemoveAt(2);

        // To print the count of elements in Collection
        Console.WriteLine("Count : " + myColl.Count);

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
Count : 5
A
B
C
D
E
Count : 4
A
B
D
E

```

**例 2:**

```cs
// C# code to remove the element
// at the specified index of the Collection
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

        // To print the count of elements in Collection
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }

        // Removing the element at the
        // specified index of the Collection
        // This should raise "ArgumentOutOfRangeException"
        // as the index is less than 0
        myColl.RemoveAt(-4);

        // To print the count of elements in Collection
        Console.WriteLine("Count : " + myColl.Count);

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

**注:**此方法为 O(n)运算，其中 n 为 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . remove at？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.removeat?view=netframework-4.7.2)