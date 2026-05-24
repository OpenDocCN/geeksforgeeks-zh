# C# | 如何检查列表是否包含指定元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-how-to-check-whether-a-list-contains-a-specified-element/](https://www.geeksforgeeks.org/c-sharp-how-to-check-whether-a-list-contains-a-specified-element/)

## `List<T>.Contains(T)` 方法

`List<T>.Contains(T)` 方法用于检查某个元素是否在列表中。

### 列表属性

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   `List` 类可以接受 `null` 作为引用类型的有效值，并且它还允许重复的元素。
*   如果 `Count` 变为等于 `Capacity`，则列表的容量通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

## 语法

```cs
public bool Contains (T item);
```

这里，`item` 是要在列表中定位的对象。对于引用类型，该值可以为 `null`。

## 返回值

如果在列表中找到该项目，则该方法返回 `true`，否则返回 `false`。

以下程序说明了 `List<T>.Contains(T)` 方法的使用：

### 示例 1

```cs
// C# Program to check whether the
// element is present in the List
// or not
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

// Adding elements to List
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);
        firstlist.Add(5);
        firstlist.Add(6);
        firstlist.Add(7);

// Checking whether 4 is present
        // in List or not
        Console.Write(firstlist.Contains(4));
    }
}
```

**输出：**

```cs
True
```

### 示例 2

```cs
// C# Program to check whether the
// element is present in the List
// or not
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating an List<T> of String
        List<String> firstlist = new List<String>();

// Adding elements to List
        firstlist.Add("Geeks");
        firstlist.Add("For");
        firstlist.Add("Geeks");
        firstlist.Add("GFG");
        firstlist.Add("C#");
        firstlist.Add("Tutorials");
        firstlist.Add("GeeksforGeeks");

// Checking whether Java is present
        // in List or not
        Console.Write(firstlist.Contains("Java"));
    }
}
```

**输出：**

```cs
False
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.contains?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.contains?view=netframework-4.7.2)