# C# | 获取排序集中的最大值

> 原文：[https://www.geeksforgeeks.org/c-sharp-get-the-maximum-value-in-the-sortedset/](https://www.geeksforgeeks.org/c-sharp-get-the-maximum-value-in-the-sortedset/)

## SortedSet 类

`SortedSet` 类表示按排序顺序排列的对象集合。这个类隶属于 `System.Collections.Generic` 命名空间。`SortedSet<T>.Max` 属性用于获取排序集中由比较器定义的最大值。

### 属性

*   在 C# 中，`SortedSet` 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 `SortedSet` 类。

### 语法

```cs
mySet.Max
```

在这里，`mySet` 是一个 `SortedSet`。

**返回值：** 排序集中的最大值。

### 例 1

```cs
// C# code to get the maximum value
// in the SortedSet
using System;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a SortedSet of integers
        SortedSet<int> mySet = new SortedSet<int>();

// Inserting elements into SortedSet
        for (int i = 0; i < 10; i++) {
            mySet.Add(i);
        }

// Displaying the maximum value in the SortedSet
        Console.WriteLine("The maximum element in SortedSet is : " + mySet.Max);
    }
}
```

**Output:**

```cs
The maximum element in SortedSet is : 9
```

### 例 2

```cs
// C# code to get the maximum value
// in the SortedSet
using System;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a SortedSet of strings
        SortedSet<string> mySet = new SortedSet<string>();

// Inserting elements into SortedSet
        mySet.Add("A");
        mySet.Add("B");
        mySet.Add("C");
        mySet.Add("D");
        mySet.Add("E");
        mySet.Add("F");

// Displaying the maximum value in the SortedSet
        Console.WriteLine("The maximum element in SortedSet is : " + mySet.Max);
    }
}
```

**Output:**

```cs
The maximum element in SortedSet is : F
```

### 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.max?view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.max?view=netcore-2.1)