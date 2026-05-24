# C# |数组列表，其元素是指定值的副本

> 原文:[https://www . geesforgeks . org/c-sharp-ArrayList-其元素是指定值的副本/](https://www.geeksforgeeks.org/c-sharp-arraylist-whose-elements-are-copies-of-the-specified-value/)

数组列表。Repeat(Object，Int32)方法用于返回数组列表，该列表的元素是指定值的副本。或者换句话说，当你想在数组列表中重复一个指定的元素时，使用这个方法**。**此方法为 O(n)运算，其中 n 为应复制项目的次数。

**语法:**

```cs
public static ArrayList Repeat (object item, int count);
```

**参数:**

> **项:**是在新数组列表中复制多次的对象。该值可以为空。
> **计数:**统计*项*应复制的次数。

**返回值:**该方法返回一个数组列表，其中包含*计数*个元素，所有元素都是*项*的副本。

**异常:**如果计数值小于零，则该方法将给出*argumentout of range Exception*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate the use of 
// ArrayList.Repeat(Object, Int32) Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // Create and repeat the element
        // of ArrayList "mylist" 
        ArrayList mylist = ArrayList.Repeat("GFG", 6);

        // Display element
        foreach(Object ob in mylist)
        {
            Console.WriteLine(ob);
        }

        // Display and count the total number of element
        Console.WriteLine("The count of the item is : {0}", mylist.Count);
    }
}
```

**Output:**

```cs
GFG
GFG
GFG
GFG
GFG
GFG
The count of the item is : 6

```

**例 2:**

```cs
// C# program to illustrate the use of 
// ArrayList.Repeat(Object, Int32) Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // Create and repeat the 
        // element of mylist ArrayList
        // this will give runtime error
        // as count is less than 0
        ArrayList mylist = ArrayList.Repeat(43, -1);

        // Display element
        foreach(Object ob in mylist)
        {
            Console.WriteLine(ob);
        }

        // Display and count the total number of element
        Console.WriteLine("The count of the item is : {0}", mylist.Count);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:计数

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . repeat？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.repeat?view=netframework-4.7.2)