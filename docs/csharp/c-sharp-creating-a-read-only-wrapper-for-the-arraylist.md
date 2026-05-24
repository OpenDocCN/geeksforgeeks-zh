# C# |为数组列表创建只读包装器

> 原文:[https://www . geeksforgeeks . org/c-sharp-为数组列表创建只读包装器/](https://www.geeksforgeeks.org/c-sharp-creating-a-read-only-wrapper-for-the-arraylist/)

**数组列表。ReadOnly(数组列表)方法**用于获取只读的[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)包装。

**语法:**

> 公共静态系统。数组列表只读(系统。Collections.ArrayList 列表)；

这里*列表*是要包装的数组列表。

**返回值:**返回一个只读数组列表包装器，用于包装*列表*。

**异常:**如果*列表*为空，该方法返回*参数异常*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to create a read-only
// wrapper for the ArrayList
using System;
using System.Collections;

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

        // Creating a Read-Only packing
        // around the ArrayList
        ArrayList myList2 = ArrayList.ReadOnly(myList);

        // --------- Using IsReadOnly Property

        // print the status of both ArrayList
        Console.WriteLine("myList ArrayList is {0}.",
                    myList.IsReadOnly ? "read-only" : 
                                    "not read-only");

        Console.WriteLine("myList2 ArrayList is {0}.",
                    myList2.IsReadOnly ? "read-only" : 
                                     "not read-only");
    }
}
```

**输出:**

```cs
myList ArrayList is not read-only.
myList2 ArrayList is read-only.

```

**例 2:**

```cs
// C# code to create a read-only 
// wrapper for the ArrayList
using System; 
using System.Collections; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating an ArrayList 
        ArrayList myList = new ArrayList(); 

        // Adding elements to ArrayList 
        myList.Add("C"); 
        myList.Add("C++"); 
        myList.Add("Java"); 
        myList.Add("C#"); 
        myList.Add("Python"); 

        Console.WriteLine("Before Wrapping: ");

        // Displaying the elements in the ArrayList 
        foreach(string str in myList) 
        { 
            Console.WriteLine(str); 
        } 

        // Creating a Read-Only packing 
        // around the ArrayList 
        ArrayList myList2 = ArrayList.ReadOnly(myList);

        Console.WriteLine("After Wrapping: ");

        // Displaying the elements 
        foreach(string str in myList2) 
        { 
            Console.WriteLine(str); 
        } 

        Console.WriteLine("Trying to add new element into myList2:");

        // it will give error
        myList2.Add("HTML");

    } 
} 
```

**输出:**

```cs
Before Wrapping: 
C
C++
Java
C#
Python
After Wrapping: 
C
C++
Java
C#
Python
Trying to add new element into myList2:

```

**运行时错误:**

> 未处理异常:
> 系统。NotSupportedException:集合是只读的。
> 在系统中。集合。数组列表+ReadOnlyArrayList。增加

**说明:**在上面的程序中，可以在 *myList* 中添加或删除元素，即原始数组列表，它将反映到只读集合中。

**注:**

*   为防止对*列表*的任何修改，仅通过此包装暴露*列表*。
*   只读集合只是一个带有防止修改集合的包装的集合。如果对基础集合进行了更改，只读集合将反映这些更改。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . readonly？view = net framework-4 . 7 . 2 # System _ Collections _ ArrayList _ ReadOnly _ System _ Collections _ ArrayList _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.readonly?view=netframework-4.7.2# System_Collections_ArrayList_ReadOnly_System_Collections_ArrayList_)