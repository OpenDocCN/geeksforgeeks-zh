# C# | 向 SortedSet 添加元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-add-element-to-sortedset/](https://www.geeksforgeeks.org/c-sharp-add-element-to-sortedset/)

`SortedSet` 类表示按排序顺序排列的对象集合。这个类隶属于 `System.Collections.Generic` 命名空间。`SortedSet<T>.Add(T)` 方法用于将元素添加到集合中，并返回一个值，该值指定元素添加是否成功。

## 属性

*   在 C# 中，`SortedSet` 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 `SortedSet` 类。

## 语法

```cs
public bool Add (T item);
```

## 参数

> `item`：添加到集合中的元素。

## 返回值

`true` 如果元素添加到集合中，否则 `false`。

## 例 1

```cs
// C# code to add element to SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        for (int i = 2; i < 7; i++) {
            mySortedSet.Add(i * 2);
        }

        // Displaying elements in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs

```

## 例 2

```cs
// C# code to add element to SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        mySortedSet.Add(4);
        mySortedSet.Add(5);
        mySortedSet.Add(6);

        // Trying to add some duplicate
        // elements in mySortedSet
        mySortedSet.Add(6);
        mySortedSet.Add(6);
        mySortedSet.Add(6);
        mySortedSet.Add(7);

        // Displaying elements in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs

```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.add?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.add?view=netframework-4.7.2)