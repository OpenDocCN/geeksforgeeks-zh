# C# |如何获取排序集中的子集

> 原文：[https://www.geeksforgeeks.org/c-sharp-how-to-get-a-subset-in-a-sortedset/](https://www.geeksforgeeks.org/c-sharp-how-to-get-a-subset-in-a-sortedset/)

`SortedSet`类表示按排序顺序排列的对象集合。这个类隶属于`System.Collections.Generic`命名空间。`SortedSet<T>.GetViewBetween(T, T)`方法用于返回`SortedSet<T>`中子集的视图。

## 属性

*   在 C# 中，`SortedSet`类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用`SortedSet`类。

## 语法

```cs
public virtual System.Collections.Generic.SortedSet<T> GetViewBetween(T lowerValue, T upperValue);
```

**参数:**
*   `lowerValue`: 视图中的最低期望值。
*   `upperValue`: 视图中的最高期望值。

**返回值:** 仅包含指定范围内的值的子集视图。

## 异常

*   `ArgumentException`: 如果`lowerValue`大于`upperValue`根据比较器。
*   `ArgumentOutOfRangeException`: 视图上的尝试操作超出了`lowerValue`和`upperValue`指定的范围。

## 例 1

```cs
// C# code to get the subset of a SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a SortedSet of strings
        SortedSet<string> mySet1 = new SortedSet<string>();

        // Inserting elements in SortedSet
        mySet1.Add("A");
        mySet1.Add("B");
        mySet1.Add("C");
        mySet1.Add("D");
        mySet1.Add("E");
        mySet1.Add("F");
        mySet1.Add("G");
        mySet1.Add("H");
        mySet1.Add("I");

        // Get the subset between "C" and "G"
        SortedSet<string> mySet2 = mySet1.GetViewBetween("C", "G");

        // Displaying the elements in the subset
        foreach(string str in mySet2)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
C
D
E
F
G
```

## 例 2

```cs
// C# code to get the subset of a SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a SortedSet of integers
        SortedSet<int> mySet1 = new SortedSet<int>();

        // Inserting elements in SortedSet
        for (int i = 0; i < 10; i++) {
            mySet1.Add(i);
        }

        // Get the subset between "3" and "7"
        SortedSet<int> mySet2 = mySet1.GetViewBetween(3, 7);

        // Displaying the elements in the subset
        foreach(int i in mySet2)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
3
4
5
6
7
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.getviewbetween?view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.getviewbetween?view=netcore-2.1)