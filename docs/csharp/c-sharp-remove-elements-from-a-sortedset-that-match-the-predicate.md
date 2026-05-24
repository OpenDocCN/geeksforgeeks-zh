# C# |从排序集中移除与谓词匹配的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-elements-from-a-sorted set-the-match-the-述词/](https://www.geeksforgeeks.org/c-sharp-remove-elements-from-a-sortedset-that-match-the-predicate/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班属于*系统。集合.通用*命名空间。**排序集合< T >。RemoveWhere(谓词< T >)方法**用于从排序集合< T >中移除所有与指定谓词定义的条件相匹配的元素。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
public int RemoveWhere (Predicate<T> match);

```

**返回值:**这个方法返回从 SortedSet < T >集合中移除的元素数量。

**异常:**如果匹配为空，该方法将给出 *ArgumentNullException* 。

**注意:**调用这个方法是一个 O(n)运算，其中 n 是[计数](https://www.geeksforgeeks.org/c-get-the-number-of-elements-in-the-sortedset/)，即 SortedSet 中包含的元素个数。

下面是举例说明**排序集< T >。移除 Where(谓词< T >)方法**

**例 1:**

```cs
// C# code to remove elements from a SortedSet
// that match the predicate
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

        Console.WriteLine("The elements in SortedSet are : ");

        // Displaying the elements in SortedSet
        foreach(int i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in SortedSet
        Console.WriteLine("Number of elements are : " + mySet.Count);

        // Remove elements from a SortedSet
        // with conditions defined by the predicate
        mySet.RemoveWhere(isEven);

        Console.WriteLine("The elements in SortedSet are : ");

        // Displaying the elements in SortedSet
        foreach(int i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in SortedSet
        Console.WriteLine("Number of elements are : " + mySet.Count);
    }

    // Helper function which tells
    // whether an element is even or not
    private static bool isEven(int i)
    {
        return ((i % 2) == 0);
    }
}
```

**Output:**

```cs
The elements in SortedSet are : 
0
1
2
3
4
5
6
7
8
9
Number of elements are : 10
The elements in SortedSet are : 
1
3
5
7
9
Number of elements are : 5

```

**例 2 :**

```cs
// C# code to remove elements from a
// SortedSet that match the predicate
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySet = new SortedSet<int>();

        // Inserting elements into SortedSet
        for (int i = 0; i < 20; i++) {
            mySet.Add(i);
        }

        // Displaying the number of elements in SortedSet
        Console.WriteLine("Number of elements are : " + mySet.Count);

        // Remove elements from a SortedSet
        // with conditions defined by the predicate
        mySet.RemoveWhere(myFunc);

        // Displaying the number of elements in SortedSet
        Console.WriteLine("Number of elements are : " + mySet.Count);
    }

    // Helper function which tells
    // whether an element is divisible
    // by both 2 and 3
    private static bool myFunc(int i)
    {
        return ((i % 2) == 0 && (i % 3 == 0));
    }
}
```

**Output:**

```cs
Number of elements are : 20
Number of elements are : 16

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . remove where？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.removewhere?view=netframework-4.7.2)