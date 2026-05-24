# C# |从源数组列表中获取元素的子集

> 原文:[https://www . geeksforgeeks . org/c-sharp-从源数组列表中获取元素子集/](https://www.geeksforgeeks.org/c-sharp-getting-a-subset-of-the-elements-from-the-source-arraylist/)

**数组列表。GetRange(Int32，Int32)方法**用于获取一个[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)，它将代表源数组列表中元素的子集。

**语法:**

```cs
public virtual System.Collections.ArrayList GetRange (int index, int count);
```

**参数:**

> **索引:**为 Int32 类型，代表范围开始的从零开始的数组列表索引。
> **计数:**为 Int32 型，代表该范围内的元素数量。

**返回值:**该方法返回一个数组列表，该列表代表源数组列表中元素的子集。

**异常:**

*   **argumentoutofrangerexception:**如果索引的值小于零， ***或者*** 如果计数的值小于零。
*   **参数异常:**如果索引和计数的值不表示数组列表中元素的有效范围。

以下程序说明了上述方法:

**例 1:**

```cs
// C# program to illustrate the
// concept of GetRange() Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // Creates and initializes
        // a new ArrayList.
        ArrayList myarraylist = new ArrayList();
        myarraylist.Add("Welcome");
        myarraylist.Add("to");
        myarraylist.Add("Geeks");
        myarraylist.Add("for");
        myarraylist.Add("Geeks");
        myarraylist.Add("portal");

        // Creates and initializes queue
        Queue mynewList = new Queue();
        mynewList.Enqueue("This");
        mynewList.Enqueue("is");
        mynewList.Enqueue("C#");
        mynewList.Enqueue("tutorial");

        // Displays the values of six 
        // elements starting at index 0.
        ArrayList newarraylist = myarraylist.GetRange(0, 6);
        Console.WriteLine("Elements are:");
        Displaydata(newarraylist, '\n');

        // Replaces the values of six elements 
        // starting at index 1 with the values
        // in the queue.
        myarraylist.SetRange(2, mynewList);

        // Displays the values of six 
        // elements starting at index 0.
        newarraylist = myarraylist.GetRange(0, 6);
        Console.WriteLine("\nNow elements are:");
        Displaydata(newarraylist, '\n');
    }

    public static void Displaydata(IEnumerable myvalueList,
                                          char mySeparator)
    {
        foreach(Object obj in myvalueList)
            Console.Write("{0}{1}", mySeparator, obj);
        Console.WriteLine();
    }
}
```

**输出:**

```cs
Elements are:

Welcome
to
Geeks
for
Geeks
portal

Now elements are:

Welcome
to
This
is
C#
tutorial

```

**例 2:**

```cs
// C# program to illustrate the
// concept of GetRange() Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // Creates and initializes a new ArrayList.
        ArrayList myarraylist = new ArrayList();
        myarraylist.Add("Welcome");
        myarraylist.Add("to");
        myarraylist.Add("Geeks");
        myarraylist.Add("for");
        myarraylist.Add("Geeks");
        myarraylist.Add("portal");

        // Creates and initializes queue
        Queue mynewList = new Queue();
        mynewList.Enqueue("This");
        mynewList.Enqueue("is");
        mynewList.Enqueue("C#");
        mynewList.Enqueue("tutorial");

        // Displays the values of six elements
        ArrayList newarraylist = myarraylist.GetRange(-1, 6);
        Console.WriteLine("Elements are:");
        Displaydata(newarraylist, '\n');

        // Replaces the values of six elements 
        // starting at index 1 with the 
        // values in the queue.
        myarraylist.SetRange(2, mynewList);

        // Displays the values of six 
        // elements starting at index 0.
        newarraylist = myarraylist.GetRange(0, 6);
        Console.WriteLine("Now elements are:");
        Displaydata(newarraylist, '\n');
    }

    public static void Displaydata(IEnumerable myvalueList, 
                                          char mySeparator)
    {
        foreach(Object obj in myvalueList)
            Console.Write("{0}{1}", mySeparator, obj);
        Console.WriteLine();
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:索引

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . getrange？view = net framework-4 . 7 . 2 # System _ Collections _ ArrayList _ GetRange _ System _ int 32 _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.getrange?view=netframework-4.7.2# System_Collections_ArrayList_GetRange_System_Int32_System_Int32_)