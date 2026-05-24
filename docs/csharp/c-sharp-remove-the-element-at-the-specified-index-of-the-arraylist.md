# C# |删除数组列表指定索引处的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-在数组列表的指定索引处移除元素/](https://www.geeksforgeeks.org/c-sharp-remove-the-element-at-the-specified-index-of-the-arraylist/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。RemoveAt(Int32)** 方法用于移除数组列表中指定索引处的元素。

**属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual void RemoveAt (int index);

```

这里，*索引*是要移除的元素的从零开始的索引。

**异常:**

*   **argumentoutofrangerexception:**如果索引小于零或索引等于或大于 Count，其中 Count 是数组列表中的元素数。
*   **notSupportDexception:**如果数组列表是只读的或者数组列表具有固定的大小。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the element at
// the specified index of ArrayList
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
        Console.WriteLine("The elements in ArrayList initially are :");

        foreach(string str in myList)
            Console.WriteLine(str);

        // Removing the element present at index 4
        myList.RemoveAt(4);

        // Displaying the elements in ArrayList
        Console.WriteLine("The elements in ArrayList are :");

        foreach(string str in myList)
            Console.WriteLine(str);
    }
}
```

**输出:**

```cs
The elements in ArrayList initially are:
A
B
C
D
E
F
The elements in ArrayList are:
A
B
C
D
F

```

**例 2:**

```cs
// C# code to remove the element at
// the specified index of ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList(10);

        // Adding elements to ArrayList
        myList.Add(2);
        myList.Add(3);
        myList.Add(4);
        myList.Add(5);
        myList.Add(6);
        myList.Add(7);

        // Removing the element present at index 7
        // It should raise System.ArgumentOutOfRangeException
        myList.RemoveAt(7);

        // Displaying the elements in ArrayList
        Console.WriteLine("The elements in ArrayList are :");

        foreach(int i in myList)
            Console.WriteLine(i);
    }
}
```

**输出:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**注:**

*   这个方法是一个 O(n)运算，其中 n 是 Count。
*   移除元素后，将调整集合的大小，并将 Count 属性的值减少 1。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . remove at？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.removeat?view=netframework-4.7.2)