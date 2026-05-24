# C# | 检查哈希集是否是指定集合的超集

> 原文：[https://www.geeksforgeeks.org/c-sharp-check-if-a-hashset-is-a-superset-of-the-specified-collection/](https://www.geeksforgeeks.org/c-sharp-check-if-a-hashset-is-a-superset-of-the-specified-collection/)

一个 `HashSet` 是**独特元素**的无序集合。属于 `System.Collections.Generic` 命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。`HashSet<T>.IsSupersetOf(IEnumerable<T>)` 方法用于检查一个 `HashSet<T>` 对象是否是指定集合的超集。

## 语法

```cs
mySet1.IsSupersetOf(mySet2);
```

在这里，`mySet1` 和 `mySet2` 是两个 `HashSet`。

## 返回值

如果 `HashSet` 对象是另一个子集的超集，该方法返回 `true`，否则返回 `false`。

## 异常

如果哈希表为 `null`，该方法将给出 `ArgumentNullException`。

下面给出了一些例子，以便更好地理解实现：

## 例 1

```cs
// C# code to Check if a HashSet is a
// superset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet1 = new HashSet<string>();

        // Inserting elements in HashSet
        mySet1.Add("Geeks");
        mySet1.Add("GeeksQuiz");

        // Creating a HashSet of strings
        HashSet<string> mySet2 = new HashSet<string>();

        // Inserting elements in HashSet
        mySet2.Add("DS");
        mySet2.Add("C++");
        mySet2.Add("Java");
        mySet2.Add("JavaScript");
        mySet2.Add("GeeksQuiz");
        mySet2.Add("Geeks");

        // Check if a HashSet is a superset
        // of the specified collection
        // It should return true as HashSet mySet2
        // is superset of HashSet mySet1
        Console.WriteLine(mySet2.IsSupersetOf(mySet1));
    }
}
```

**Output:**

```cs
True
```

## 例 2

```cs
// C# code to Check if a HashSet is a
// superset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Inserting elements in HashSet
        mySet1.Add(2);
        mySet1.Add(3);
        mySet1.Add(4);
        mySet1.Add(5);

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements in HashSet
        mySet2.Add(3);
        mySet2.Add(4);
        mySet2.Add(5);
        mySet2.Add(6);

        // Check if a HashSet is a superset
        // of the specified collection
        // It should return false as HashSet mySet2
        // is not a superset of HashSet mySet1
        Console.WriteLine(mySet2.IsSupersetOf(mySet1));
    }
}
```

**Output:**

```cs
False
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.issupersetof?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.issupersetof?view=netframework-4.7.2)