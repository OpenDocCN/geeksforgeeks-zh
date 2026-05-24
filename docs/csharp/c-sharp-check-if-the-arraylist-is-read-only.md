# C# |检查数组列表是否为只读

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-the-ArrayList-只读/](https://www.geeksforgeeks.org/c-sharp-check-if-the-arraylist-is-read-only/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。IsReadOnly** 属性用于检查数组列表是否为只读。

**属性:**

*   Elements can be added or removed from the array list collection at any point in time.
*   Arrays do not guarantee sorting.
*   The capacity of the array is the number of elements that the array list can hold.
*   You can access the elements in this collection using an integer index. The index in this collection is zero-based.
*   Duplicate elements are also allowed.
*   Multidimensional arrays are not supported as elements in array list collections.

**语法:**

```cs
public virtual bool IsReadOnly { get; }

```

**返回值:**如果数组列表是只读的，这个方法返回 ***真*** ，否则返回 ***假*** 。默认值为 ***假*** 。

**示例:**

```cs
// C# code to check if the ArrayList
// is read-only or not
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add("Geeks");
        myList.Add("for");
        myList.Add("Geeks");
        myList.Add("Noida");
        myList.Add("Geeks Classes");
        myList.Add("Delhi");

        // To check if the ArrayList is read-only or not
        Console.WriteLine(myList.IsReadOnly);
    }
}
```

**Output:**

```cs
False

```

**注意:**

*   The read-only collection is not allowed to add, remove or modify elements after it is created.
*   Retrieving the value of this attribute is an O(1) operation.

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。收藏品。数组列表。是只读的。视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.isreadonly?view=netframework-4.7.2)