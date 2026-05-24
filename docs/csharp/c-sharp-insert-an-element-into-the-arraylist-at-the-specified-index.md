# C# |在数组列表中指定的索引处插入一个元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-将元素插入指定索引处的数组列表/](https://www.geeksforgeeks.org/c-sharp-insert-an-element-into-the-arraylist-at-the-specified-index/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。Insert(Int32，Object)** 方法将一个元素插入到数组列表的指定索引处。

**数组列表类的属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual void Insert (int index, object value);

```

**参数:**

> **索引:**是应该插入值的从零开始的索引。
> 
> **值:**是要插入的对象。*值*可以为空。

**异常:**

*   **argumentoutofrangerexception:**如果索引小于零或索引大于计数，即数组列表中的元素数量。
*   **notSupportDexception:**如果数组列表是只读的或者数组列表具有固定的大小。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to insert an element
// into the ArrayList at the
// specified index
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

        // Displaying the elements in ArrayList
        Console.WriteLine("The initial ArrayList is : ");
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }

        // Inserting 3 elements at random index in the ArrayList
        myList.Insert(1, "D");
        myList.Insert(4, "E");
        myList.Insert(5, "F");

        // Displaying the modified ArrayList
        Console.WriteLine("The ArrayList after Inserting elements is : ");

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
The initial ArrayList is : 
A
B
C
The ArrayList after Inserting elements is : 
A
D
B
C
E
F

```

**例 2:**

```cs
// C# code to insert an element
// into the ArrayList at the
// specified index
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
        myList.Add(1);
        myList.Add(2);
        myList.Add(3);

        // Displaying the elements in ArrayList
        Console.WriteLine("The initial ArrayList is : ");
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }

        // Inserting 3 elements in front of the ArrayList
        myList.Insert(0, 4);
        myList.Insert(0, 5);
        myList.Insert(0, 6);

        // Displaying the modified ArrayList
        Console.WriteLine("The ArrayList after Inserting elements is : ");

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
The initial ArrayList is : 
1
2
3
The ArrayList after Inserting elements is : 
6
5
4
1
2
3

```

**注:**

*   如果索引等于计数，即数组列表中的元素数量，则数组列表的末尾会添加一个值。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . insert？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.insert?view=netframework-4.7.2)