# C# |检查数组列表中是否包含元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-一个元素是否包含在数组列表中/](https://www.geeksforgeeks.org/c-sharp-check-whether-an-element-is-contained-in-the-arraylist/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。Contains(Object)** 方法确定数组列表中是否存在该元素。

**数组列表类的属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual bool Contains (object item);

```

这里，*项*是数组列表中要定位的对象。该值可以为空。

**返回值:**如果在*数组列表*中找到该项目，该方法将返回*真*，否则返回*假*。

**注:**该方法执行线性搜索，因此，该方法为 *O(n)* 运算，其中 *n* 为 Count。

下面是说明**数组列表的程序。包含(对象)**方法:

**例 1:**

```cs
// C# code to check if an element is
// contained in ArrayList or not
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
        myList.Add("G");
        myList.Add("H");

        // To check if the ArrayList Contains element "E"
        // If yes, then display it's index, else
        // display the message
        if (myList.Contains("E"))
            Console.WriteLine("Yes, exists at index " + myList.IndexOf("E"));
        else
            Console.WriteLine("No, doesn't exists");
    }
}
```

**Output:**

```cs
Yes, exists at index 4

```

**例 2 :**

```cs
// C# code to check if an element is
// contained in ArrayList or not
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
        myList.Add("5");
        myList.Add("7");
        myList.Add("9");
        myList.Add("11");
        myList.Add("12");
        myList.Add("16");
        myList.Add("20");
        myList.Add("25");

        // To check if the ArrayList Contains element "24"
        // If yes, then display it's index, else
        // display the message
        if (myList.Contains("24"))
            Console.WriteLine("Yes, exists at index " + myList.IndexOf("24"));
        else
            Console.WriteLine("No, doesn't exists");
    }
}
```

**Output:**

```cs
No, doesn't exists

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.contains?view=netframework-4.7.2)