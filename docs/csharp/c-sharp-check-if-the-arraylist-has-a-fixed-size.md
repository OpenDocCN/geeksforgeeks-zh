# C# |检查数组列表是否有固定大小

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-the-ArrayList-具有固定大小/](https://www.geeksforgeeks.org/c-sharp-check-if-the-arraylist-has-a-fixed-size/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。IsFixedSize** 属性用于检查数组列表是否有固定大小。

**属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual bool IsFixedSize { get; }

```

**返回值:**如果数组列表有固定的大小，这个方法返回 ***真*** ，否则返回 ***假*** 。默认值为 ***假*** 。

下面的程序说明了**数组列表的使用。IsFixedSize 属性**:

**例 1:**

```cs
// C# code to check if the ArrayList
// has fixed size or not
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
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");
        myList.Add("E");
        myList.Add("F");

        // To check if the ArrayList has fixed size or not
        Console.WriteLine(myList.IsFixedSize);
    }
}
```

**Output:**

```cs
False

```

**例 2:**

```cs
// C# code to check if the ArrayList 
// has fixed size or not 
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
        myList.Add("1"); 
        myList.Add("2"); 
        myList.Add("3"); 
        myList.Add("4"); 
        myList.Add("5"); 
        myList.Add("6"); 

        // To check if the ArrayList 
        // has fixed size or not
        // it will return false
        Console.WriteLine(myList.IsFixedSize); 

        // Create a fixed-size wrapper
        // around the ArrayList
        ArrayList myListfixed = ArrayList.FixedSize(myList);

        // To check if the ArrayList
        // has fixed size or not
        // it will return true
        Console.WriteLine(myListfixed.IsFixedSize); 

    } 
} 
```

**输出:**

```cs
False
True

```

**注:**

*   具有固定大小的集合不允许在创建集合后添加或移除元素，但允许修改现有元素。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . isfixedsize？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.isfixedsize?view=netframework-4.7.2)