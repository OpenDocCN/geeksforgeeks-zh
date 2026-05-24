# C# 获取 SortedList 对象中的值

> 原文：[https://www.geeksforgeeks.org/c-sharp-getting-the-values-in-a-sortedlist-object/](https://www.geeksforgeeks.org/c-sharp-getting-the-values-in-a-sortedlist-object/)

## `SortedList.Values` 属性

`SortedList.Values` 属性用于获取 `SortedList` 对象中的值。

### 语法

```csharp
public virtual System.Collections.ICollection Values { get; }
```

**属性值：** 包含 `SortedList` 对象中的值的集合对象。

以下程序说明了上述属性的使用：

### 示例 1

```csharp
// C# code to get an ICollection containing
// the values in the SortedList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedList
        SortedList mylist = new SortedList();

        // Adding elements in SortedList
        mylist.Add("g", "geeks");
        mylist.Add("c", "c++");
        mylist.Add("d", "data structures");
        mylist.Add("q", "quiz");

        // Get a collection of the values
        ICollection c = mylist.Values;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + mylist[str]);
    }
}
```

**输出：**

```csharp
c++
data structures
geeks
quiz
```

### 示例 2

```csharp
// C# code to get an ICollection containing
// the values in the SortedList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedList
        SortedList mylist = new SortedList();

        // Adding elements in SortedList
        mylist.Add("India", "Country");
        mylist.Add("Chandigarh", "City");
        mylist.Add("Mars", "Planet");
        mylist.Add("China", "Country");

        // Get a collection of the values
        ICollection c = mylist.Values;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + mylist[str]);
    }
}
```

**输出：**

```csharp
City
Country
Country
Planet
```

### 注意

*   [`ICollection`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2) 对象是 `SortedList` 对象的值的只读视图。对基础 `SortedList` 所做的修改会立即反映在 `ICollection` 中。
*   `ICollection` 的元素按照与 `SortedList` 的值相同的顺序进行排序。
*   该属性类似于 `GetValueList` 方法，但返回一个 `ICollection` 对象，而不是 `IList` 对象。
*   这个方法是一个 O(1) 运算。

### 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.values?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.values?view=netframework-4.7.2)