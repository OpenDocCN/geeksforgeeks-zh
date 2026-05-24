# C# |检查哈希集是否是指定集合的适当超集

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-hashset-is-a-perset-the-specific-collection/](https://www.geeksforgeeks.org/c-sharp-check-if-a-hashset-is-a-proper-superset-of-the-specified-collection/)

一个 **HashSet** 是一个独特元素的无序集合。它属于*T3 系统。集合.通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。
**HashSet <t>。方法</t>** 用于检查散列集合是否是指定集合的适当超集。

**语法:**

```cs
mySet1.IsProperSupersetOf(mySet2);

```

这里*我自己 1* 和*我自己 2* 是 2 个 HashSets。

**返回值:**如果*本人 1* 是*本人 2* 的适当超集，则函数返回*真*，否则返回*假*。

**异常:**如果 HashSet 为空，这个方法会给出 *ArgumentNullException* 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Check if a HashSet is a proper
// superset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Inserting elements into HashSet mySet1
        for (int i = 10; i < 20; i++) {
            mySet1.Add(i);
        }

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements into HashSet mySet2
        for (int i = 0; i < 25; i++) {
            mySet2.Add(i);
        }

        // Checking if mySet1 is Proper Superset Of mySet2
        // The function returns true if the condition
        // satisfies, else returns false
        Console.WriteLine(mySet1.IsProperSupersetOf(mySet2));
    }
}
```

**Output:**

```cs
False

```

**例 2:**

```cs
// C# code to Check if a HashSet is a proper
// superset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet1 = new HashSet<string>();

        // Inserting elements into HashSet mySet1
        mySet1.Add("India");
        mySet1.Add("Japan");
        mySet1.Add("USA");
        mySet1.Add("Spain");
        mySet1.Add("Italy");

        // Creating a HashSet of strings
        HashSet<string> mySet2 = new HashSet<string>();

        // Inserting elements into HashSet mySet2
        mySet2.Add("USA");
        mySet2.Add("Spain");
        mySet2.Add("Italy");

        // Checking if mySet1 is Proper Superset Of mySet2
        // The function returns true if the condition
        // satisfies, else returns false
        Console.WriteLine(mySet1.IsProperSupersetOf(mySet2));
    }
}
```

**Output:**

```cs
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . ispropertresupertof？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.ispropersupersetof?view=netframework-4.7.2)