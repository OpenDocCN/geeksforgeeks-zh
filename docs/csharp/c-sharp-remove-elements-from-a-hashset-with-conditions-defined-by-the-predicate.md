# C# |用谓词

定义的条件从哈希集中移除元素

> 原文:[https://www . geesforgeks . org/c-sharp-remove-elements-from-a-hashset-with-conditions-由谓词定义/](https://www.geeksforgeeks.org/c-sharp-remove-elements-from-a-hashset-with-conditions-defined-by-the-predicate/)

一个 **HashSet** 是一个独特元素的无序集合。它属于*体系。集合.通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。

**HashSet < T >。RemoveWhere(谓词< T > )** 方法用于从 HashSet < T >集合中移除所有与指定谓词定义的条件相匹配的元素。

**语法:**

```cs
public int RemoveWhere (Predicate<T> match);

```

**返回值:**这个方法返回从 HashSet < T >集合中移除的元素数量。

**异常:**如果匹配为空，该方法将给出*参数异常*。

**注意:**调用这个方法是一个 O(n)运算，其中 n 是 Count，即集合中包含的元素个数。

以下是说明使用 **HashSet < T >的程序。移除 Where(谓词< T >)方法:**

**例 1:**

```cs
// C# code to remove elements from a HashSet
// with conditions defined by the predicate
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // Inserting elements into HashSet
        for (int i = 0; i < 10; i++) {
            mySet.Add(i);
        }

        Console.WriteLine("The elements in HashSet are : ");

        // Displaying the elements in HashSet
        foreach(int i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in HashSet
        Console.WriteLine("Number of elements are : " + mySet.Count);

        // Remove elements from a HashSet
        // with conditions defined by the predicate
        mySet.RemoveWhere(isEven);

        Console.WriteLine("The elements in HashSet are : ");

        // Displaying the elements in HashSet
        foreach(int i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in HashSet
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
The elements in HashSet are : 
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
The elements in HashSet are : 
1
3
5
7
9
Number of elements are : 5

```

**例 2:**

```cs
// C# code to remove elements from a HashSet
// with conditions defined by the predicate
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // Inserting elements into HashSet
        for (int i = 0; i < 20; i++) {
            mySet.Add(i);
        }

        // Displaying the number of elements in HashSet
        Console.WriteLine("Number of elements are : " + mySet.Count);

        // Remove elements from a HashSet
        // with conditions defined by the predicate
        mySet.RemoveWhere(myFunc);

        // Displaying the number of elements in HashSet
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . remove where？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.removewhere?view=netframework-4.7.2)