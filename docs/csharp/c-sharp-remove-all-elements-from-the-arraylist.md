# C# |从数组列表中移除所有元素

> 原文:[https://www . geesforgeks . org/c-sharp-从数组列表中移除所有元素/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-the-arraylist/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。清除**方法用于从数组列表中移除所有元素。

**属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual void Clear ();

```

**异常:**如果数组列表是只读的或者数组列表有固定的大小，这个方法将给出 *NotSupportedException* 。

**注:**

*   这个方法是一个 O(n)运算，其中 n 是 Count。
*   Count 被设置为零，并且集合元素对其他对象的引用也被释放。
*   容量保持不变。

下面的程序说明了数组列表的使用。清除方法:

**例 1 :**

```cs
// C# code to remove all elements
// from an ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList(10);

        // Adding elements to ArrayList
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");
        myList.Add("E");
        myList.Add("F");

        // Displaying the elements in ArrayList
        Console.WriteLine("Number of elements in ArrayList initially : " 
                                                        + myList.Count);

        // Removing all elements from ArrayList
        myList.Clear();

        // Displaying the elements in ArrayList
        // after Removing all the elements
        Console.WriteLine("Number of elements in ArrayList : " + myList.Count);
    }
}
```

**Output:**

```cs
Number of elements in ArrayList initially : 6
Number of elements in ArrayList : 0

```

**例 2:**

```cs
// C# code to remove all elements
// from an ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList(10);

        // Adding elements to ArrayList
        myList.Add(3);
        myList.Add(5);
        myList.Add(7);
        myList.Add(9);
        myList.Add(11);

        // Displaying the elements in ArrayList
        Console.WriteLine("Number of elements in ArrayList initially : " 
                                                        + myList.Count);

        // Removing all elements from ArrayList
        myList.Clear();

        // Displaying the elements in ArrayList
        // after Removing all the elements
        Console.WriteLine("Number of elements in ArrayList : " + myList.Count);
    }
}
```

**Output:**

```cs
Number of elements in ArrayList initially : 5
Number of elements in ArrayList : 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.clear?view=netframework-4.7.2)