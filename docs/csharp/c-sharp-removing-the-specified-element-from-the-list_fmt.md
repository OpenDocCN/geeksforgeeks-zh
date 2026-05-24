# C#
## 从列表中删除指定元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-removing-the-specified-element-from-the-list/](https://www.geeksforgeeks.org/c-sharp-removing-the-specified-element-from-the-list/)

`List.Remove(T)`方法用于从列表中移除特定对象的第一个出现。

**列表属性：**

*   它不同于数组。一个列表可以动态调整大小，但是数组不能。
*   `List`类可以接受`null`作为引用类型的有效值，并且它也允许重复元素。
*   如果`Count`等于`Capacity`，则通过重新分配内部数组，列表的容量会自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法：**

```cs
public bool Remove (T item);
```

**参数：**

> `item`：要从列表中删除的指定对象。

**返回类型：** 如果`item`移除成功，此方法返回`true`。否则返回`false`。

**注意：** 如果列表中没有`item`，则此方法返回`false`。

下面的程序说明了如何从列表中删除指定的元素：

**例 1：**

```cs
// C# program to remove the specified
// element from the List<T>
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating a List of integers
        List<int> firstlist = new List<int>();

// adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

// Displaying elements of firstlist
        // by using foreach loop
        Console.WriteLine("Before Removing");
        foreach(int element in firstlist)
        {
            Console.WriteLine(element);
        }

// Removing 2 from the firstlist & Displaying
        // the remaining firstlist elements
        Console.WriteLine("After Removing");
        firstlist.Remove(2);
        foreach(int element in firstlist)
        {
            Console.WriteLine(element);
        }
    }
}
```

**输出：**

```cs
Before Removing
1
2
3
4
After Removing
1
3
4
```

**例 2：**

```cs
// C# program to remove the specified
// element from the List<T>
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating a List of integers
        List<int> firstlist = new List<int>();

// adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

// Adding some duplicate
        // elements in firstlist
        firstlist.Add(2);
        firstlist.Add(4);

// Displaying elements of firstlist
        // by using foreach loop
        Console.WriteLine("Before Removing");
        foreach(int element in firstlist)
        {
            Console.WriteLine(element);
        }

// Removing first occurrence of 2
        // from the firstlist & Displaying
        // the remaining firstlist elements
        Console.WriteLine("After Removing");
        firstlist.Remove(2);
        foreach(int element in firstlist)
        {
            Console.WriteLine(element);
        }
    }
}
```

**输出：**

```cs
Before Removing
1
2
3
4
2
4
After Removing
1
3
4
2
4
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.remove?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.remove?view=netframework-4.7.2)