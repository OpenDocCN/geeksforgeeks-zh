# C# |在数组列表的末尾添加一个对象

> 原文:[https://www . geeksforgeeks . org/c-sharp-将对象添加到数组末尾列表/](https://www.geeksforgeeks.org/c-sharp-add-an-object-to-the-end-of-the-arraylist/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。Add(Object)** 方法在数组列表的末尾添加一个对象。

**数组列表类的属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual int Add (object value);

```

这里，*值*是要添加到数组列表末尾的对象。该值可以为空。

**返回值:**这个方法返回数组列表索引，在该索引处添加了值。

**异常:**如果数组列表是只读的或者是固定大小的，这个方法将给出 *NotSupportedException* 。

下面是说明**数组列表使用的程序。添加(对象)**方法:

**例 1:**

```cs
// C# code to add an object to
// the end of the ArrayList
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

        // Displaying the elements in the ArrayList
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
A
B
C
D
E
F

```

**例 2:**

```cs
// C# code to add an object to
// the end of the ArrayList
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
        myList.Add(1);
        myList.Add(2);
        myList.Add(3);
        myList.Add(4);
        myList.Add(5);
        myList.Add(6);

        // Displaying the elements in the ArrayList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
1
2
3
4
5
6

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.add?view=netframework-4.7.2)