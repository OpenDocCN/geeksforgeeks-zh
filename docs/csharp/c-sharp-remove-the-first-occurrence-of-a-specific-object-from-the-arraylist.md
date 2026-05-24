# C# |从数组列表中删除特定对象的第一次出现

> 原文:[https://www . geesforgeks . org/c-sharp-从数组列表中删除第一个出现的特定对象/](https://www.geeksforgeeks.org/c-sharp-remove-the-first-occurrence-of-a-specific-object-from-the-arraylist/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。移除(对象)**方法用于从数组列表中移除特定对象的第一个匹配项。

**属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual void Remove (object obj);

```

这里， ***obj*** 是要从数组列表中移除的对象。该值可以为空。

**异常:**如果数组列表是只读的或者有固定的大小，这个方法将给出 *NotSupportedException* 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the first 
// occurrence of a specific 
// object from the ArrayList
using System; 
using System.Collections; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating an ArrayList 
        ArrayList myList = new ArrayList(10); 

        // Adding elements to ArrayList 
        myList.Add("C"); 
        myList.Add("C#"); 
        myList.Add("Java"); 
        myList.Add("C#"); 
        myList.Add("PHP"); 
        myList.Add("C#"); 

        // Displaying the elements in ArrayList 
        Console.WriteLine("The elements in ArrayList initially are :"); 

        foreach(string str in myList) 
            Console.WriteLine(str); 

        // Removing the first 
        // occurrence of C#
        myList.Remove("C#"); 

        // Displaying the elements in ArrayList 
        Console.WriteLine("The elements in ArrayList are :"); 

        foreach(string str in myList) 
            Console.WriteLine(str); 
    } 
} 
```

**输出:**

```cs
The elements in ArrayList initially are :
C
C#
Java
C#
PHP
C#
The elements in ArrayList are :
C
Java
C#
PHP
C#

```

**例 2:**

```cs
// C# code to remove the first 
// occurrence of a specific 
// object from the ArrayList
using System; 
using System.Collections; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating an ArrayList 
        ArrayList myList = new ArrayList(10); 

        // Adding elements to ArrayList 
        myList.Add("Geeks"); 
        myList.Add("Noida"); 
        myList.Add("Classes"); 
        myList.Add("GFG"); 
        myList.Add("DS"); 
        myList.Add("Algorithms"); 

        // Displaying the elements in ArrayList 
        Console.WriteLine("The elements in ArrayList initially are :"); 

        foreach(string str in myList) 
            Console.WriteLine(str); 

        // Removing the first 
        // occurrence of HTML
        // As HTML is not present so
        // it return the ArrayList as it is
        myList.Remove("HTML"); 

        // Displaying the elements in ArrayList 
        Console.WriteLine("The elements in ArrayList are :"); 

        foreach(string str in myList) 
            Console.WriteLine(str); 
    } 
} 
```

**输出:**

```cs
The elements in ArrayList initially are :
Geeks
Noida
Classes
GFG
DS
Algorithms
The elements in ArrayList are :
Geeks
Noida
Classes
GFG
DS
Algorithms

```

**注:**

*   这个方法执行线性搜索，因此，这个方法是一个 O(n)运算，其中 n 是 Count。
*   如果数组列表不包含指定的对象，则数组列表保持不变。不会引发异常。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.remove?view=netframework-4.7.2)