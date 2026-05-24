# 列表。C# 中的 `FindIndex()`方法，示例

> 原文：[https://www.geeksforgeeks.org/list-findindex-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/list-findindex-method-in-c-sharp-with-examples/)

`List<T>.FindIndex` 方法用于搜索与指定谓词定义的条件相匹配的元素，并返回 `List<T>` 中第一个匹配项的索引。如果没有找到符合条件的项目，那么这个方法将返回-1。此方法的重载列表中有 3 种方法，如下所示：

*   `FindIndex(Predicate<T>)` 方法
*   `FindIndex(Int32, Predicate<T>)` 方法
*   `FindIndex(Int32, Int32, Predicate<T>)` 方法

## `FindIndex(Predicate<T>)` 方法

此方法用于搜索与指定谓词定义的条件相匹配的元素，并返回整个 `List<T>` 中第一个匹配项的从零开始的索引。

> **语法：** `public int FindIndex(Predicate<T> match);`
>
> **参数：**
> **match**：是 `Predicate<T>` 委托，定义了要搜索的元素的条件。

**返回值：** 如果找到，返回与 **match** 定义的条件匹配的元素的第一次出现的索引。如果没有找到，则返回-1。

**异常：** 如果 **match** 为 `null`，此方法将给出 `ArgumentNullException`。

**示例：**

```cs
// C# program to demonstrate the use of
// List<T>.FindIndex (Predicate <T>) method
using System;
using System.Collections.Generic;

class GFG1 : IComparable {
    public String gg {
        get;
        set;
    }

    public int CompareTo(Object o) {
        GFG1 e = o as GFG1;
        if (e == null)
            throw new ArgumentException("Not valid object");
        return gg.CompareTo(e.gg);
    }
}

class GFG2 {
    String s;

    public GFG2(String ss) {
        s = ss;
    }

    public bool StartsWith(GFG1 e) {
        return e.gg.StartsWith(s, StringComparison.InvariantCultureIgnoreCase);
    }
}

// Driver Class
class GFG3 {
    // Main Method
    public static void Main() {
        var e = new List<GFG1>();

        // List elements
        e.AddRange(new GFG1[] {
            new GFG1{
                gg = "c",
            },
            new GFG1{
                gg = "c++",
            },
            new GFG1{
                gg = "java",
            },
            new GFG1{
                gg = "C#",
            },
            new GFG1{
                gg = "Python",
            },
            new GFG1{
                gg = "Perl",
            },
        });

        e.Sort(); // sorts the list

        var es = new GFG2("C");
        Console.WriteLine("'C' starts at index "
                  + e.FindIndex(es.StartsWith));

        es = new GFG2("P");
        Console.WriteLine("'P' starts at index " +
                  e.FindIndex(es.StartsWith));
    }
}
```

**Output:**

```cs
'C' starts at index 0
'P' starts at index 4
```

## `FindIndex(Int32, Predicate<T>)` 方法

此方法搜索与指定谓词定义的条件匹配的元素，并返回列表中从指定索引到最后一个元素的元素范围内第一个匹配项的索引。

> **语法：** `public int FindIndex(int startIndex, Predicate<T> match);`
>
> **参数：**
> **startIndex**：是搜索的从零开始的起始索引。
> **match**：是 `Predicate<T>` 委托，定义了要搜索的元素的条件。

**返回值：** 如果找到符合 **match** 定义条件的元素，该方法将返回该元素第一次出现的索引。如果没有找到，则返回-1。

**异常：**

*   `ArgumentNullException`：如果 **match** 为 `null`。
*   `ArgumentOutOfRangeException`：如果 **startIndex** 在 `List<T>` 的有效索引范围之外。

**示例：**

```cs
// C# program to demonstrate the use of
// List<T>.FindIndex (Int32, Predicate <T>) method
using System;
using System.Collections.Generic;

class GFG1 : IComparable {
    public String gg {
        get;
        set;
    }

    public int CompareTo(Object o) {
        GFG1 e = o as GFG1;
        return gg.CompareTo(e.gg);
    }
}

class GFG2 {
    String s;

    public GFG2(String ss) {
        s = ss;
    }

    public bool StartsWith(GFG1 e) {
        return e.gg.StartsWith(s, StringComparison.InvariantCultureIgnoreCase);
    }
}

// Driver Class
class GFG3 {
    // Main Method
    public static void Main() {
        var e = new List<GFG1>();

        // List elements
        e.AddRange(new GFG1[] {
            new GFG1{
                gg = "c",
            },
            new GFG1{
                gg = "Python",
            },
            new GFG1{
                gg = "Java",
            },
            new GFG1{
                gg = "C#",
            },
            new GFG1{
                gg = "Java",
            },
            new GFG1{
                gg = "Perl",
            },
        });

        // sorts the list
        e.Sort();

        var es = new GFG2("C");
        // Search for c start from index 1
        Console.WriteLine("Search for 'C' starts at index "
                  + e.FindIndex(1, es.StartsWith));

        es = new GFG2("J");
        // search for j starts from index 2
        Console.WriteLine("Search for 'J' starts at index "
                  + e.FindIndex(2, es.StartsWith));
    }
}
```

**Output:**

```cs
Search for 'C' starts at index 1
Search for 'J' starts at index 2
```

## `FindIndex(Int32, Int32, Predicate<T>)` 方法

此方法搜索与指定谓词定义的条件匹配的元素，并返回列表中从指定索引开始并包含指定元素数的元素范围内第一个匹配项的从零开始的索引。

> **语法：** `public int FindIndex(int startIndex, int count, Predicate<T> match);`
>
> **参数：**
> **startIndex**：是搜索的从零开始的起始索引。
> **count**：是要搜索的区段中的元素数量。
> **match**：是 `Predicate<T>` 委托，定义了要搜索的元素的条件。

**返回值：** 如果找到符合 **match** 定义条件的元素，该方法将返回该元素第一次出现的索引。如果没有找到，则返回-1。

**异常：**

*   `ArgumentNullException`：如果 **match** 为 `null`。
*   `ArgumentOutOfRangeException`：如果 **startIndex** 在 `List<T>` 中无效，或 **count** 小于 0，或 **startIndex** 和 **count** 没有在 `List<T>` 中指定有效的部分。

**示例：**

```cs
// C# program to demonstrate the use of
// List<T>.FindIndex (Int32, Int32,
// Predicate <T>) method
using System;
using System.Collections.Generic;

class GFG1 : IComparable {
    public String gg {
        get;
        set;
    }

    public int CompareTo(Object o) {
        GFG1 e = o as GFG1;
        return gg.CompareTo(e.gg);
    }
}

class GFG2 {
    String s;

    public GFG2(String ss) {
        s = ss;
    }

    public bool StartsWith(GFG1 e) {
        return e.gg.StartsWith(s, StringComparison.InvariantCultureIgnoreCase);
    }
}

// Driver Class
class GFG3 {
    // Main Method
    public static void Main() {
        var e = new List<GFG1>();

        // List elements
        e.AddRange(new GFG1[] {
            new GFG1{
                gg = "c",
            },
            new GFG1{
                gg = "Python",
            },
            new GFG1{
                gg = "C++",
            },
            new GFG1{
                gg = "Java",
            },
            new GFG1{
                gg = "C#",
            },
            new GFG1{
                gg = "Perl",
            },
        });

        // sorts the list
        e.Sort();

        var es = new GFG2("C");
        // search for c start from index 1
        // count is 2 here
        Console.WriteLine("Search for 'C' starts at index "
                   + e.FindIndex(0, 2, es.StartsWith));

        es = new GFG2("J");
        // search for j starts from index 2
        // count is 4 here
        Console.WriteLine("Search for 'J' starts at index "
                   + e.FindIndex(2, 4, es.StartsWith));
    }
}
```

**Output:**

```cs
Search for 'C' starts at index 0
Search for 'J' starts at index 3
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.findindex?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.findindex?view=netframework-4.7.2)