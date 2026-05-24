# C# |从数组列表中删除一系列元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-从数组列表中移除元素范围/](https://www.geeksforgeeks.org/c-sharp-remove-a-range-of-elements-from-the-arraylist/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。RemoveRange(Int32，Int32)** 方法用于从数组列表中移除一系列元素。

**数组列表类的属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual void RemoveRange (int index, int count);

```

**参数:**

> **索引:**是要移除的元素范围的从零开始的索引。
> 
> **计数:**是要删除的元素数量。

**异常:**

*   **argumentoutofrangerexception:**如果指数小于零或**T3】计数 T5】小于零。**
*   **参数异常:**如果索引和计数不表示数组列表中元素的有效范围。
*   **notSupportDexception:**如果数组列表是只读的或者数组列表具有固定的大小。

**注:**此方法为 O(n)运算，其中 n 为 Count。

下面的程序说明了**数组列表的使用。RemoveRange(Int32，Int32)** 方法:

**例 1:**

```cs
// C# code to remove a range of
// elements from the ArrayList
using System;
using System.Collections;
using System.Collections.Generic;

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
        myList.Add("G");
        myList.Add("H");
        myList.Add("I");
        myList.Add("J");

        // Displaying the elements in ArrayList
        Console.WriteLine("The initial ArrayList is: ");

        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }

        // removing 2 elements starting from index 2
        myList.RemoveRange(2, 2);

        // Displaying the modified ArrayList
        Console.WriteLine("The ArrayList after Removing elements: ");

        // Displaying the elements in ArrayList
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
The initial ArrayList is: 
A
B
C
D
E
F
G
H
I
J
The ArrayList after Removing elements: 
A
B
E
F
G
H
I
J

```

**例 2:**

```cs
// C# code to remove a range of
// elements from the ArrayList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList(10);

        // Adding elements to ArrayList
        myList.Add(2);
        myList.Add(4);
        myList.Add(6);
        myList.Add(8);
        myList.Add(10);
        myList.Add(12);
        myList.Add(14);
        myList.Add(16);
        myList.Add(18);
        myList.Add(20);

        // Displaying the elements in ArrayList
        Console.WriteLine("The initial ArrayList: ");

        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }

        // removing 4 elements starting from index 0
        myList.RemoveRange(0, 4);

        // Displaying the modified ArrayList
        Console.WriteLine("The ArrayList after Removing elements: ");

        // Displaying the elements in ArrayList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The initial ArrayList is: 
2
4
6
8
10
12
14
16
18
20
The ArrayList after Removing elements: 
10
12
14
16
18
20

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . remove range？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.removerange?view=netframework-4.7.2)