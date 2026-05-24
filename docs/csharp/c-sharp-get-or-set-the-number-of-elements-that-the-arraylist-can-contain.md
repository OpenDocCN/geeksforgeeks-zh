# C# |获取或设置数组列表可以包含的元素数量

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-or-set-ArrayList 所能包含的元素数量/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-that-the-arraylist-can-contain/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。Capacity** 属性用于获取或设置数组列表可以包含的元素数量。

**数组列表类的属性:**

*   Elements can be added or removed from the array list collection at any point in time.
*   Arrays do not guarantee sorting.
*   The capacity of the array is the number of elements that the array list can hold.
*   You can access the elements in this collection using an integer index. The index in this collection is zero-based.
*   Duplicate elements are also allowed.
*   Multidimensional arrays are not supported as elements in array list collections.

**语法:**

```cs
public virtual int Capacity { get; set; }

```

**返回值:**数组列表可以包含的元素数量。

**异常:**

*   **argumentoutofrangerexception:**如果容量设置为小于计数的值，即数组列表中的元素数量。
*   **OutOfMemoryException :** 如果系统上没有足够的可用内存。

**例:**

```cs
// C# code to get or set the number 
// of elements that the ArrayList can contain
using System; 
using System.Collections;

class GFG {

// Driver code
public static void Main() { 

    // Creating an ArrayList
    ArrayList myList = new ArrayList();

    // Adding elements to ArrayList
    myList.Add(1);
    myList.Add(2);
    myList.Add(3);
    myList.Add(4);
    myList.Add(5);

    // Displaying count of elements of ArrayList
    Console.WriteLine("Number of elements: " + myList.Count); 

    // Displaying Current capacity of ArrayList
    Console.WriteLine("Current capacity: " + myList.Capacity); 
} 
}
```

**输出:**

```cs
Number of elements: 5
Current capacity: 8

```

**要点:**

*   Capacity is the number of elements that the array list can store. **[Count](https://www.geeksforgeeks.org/c-get-the-number-of-elements-actually-contained-in-the-arraylist/)** is the actual number of elements in the array list.
*   The capacity is always greater than or equal to **[count](https://www.geeksforgeeks.org/c-get-the-number-of-elements-actually-contained-in-the-arraylist/)** . If the count exceeds the capacity when adding elements, the capacity will be automatically increased by reallocating the internal array before copying the old elements and adding new elements.

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。收藏品。数组列表。容量？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.capacity?view=netframework-4.7.2)