# C# |两个 HashSet 的并集

> 原文:[https://www.geeksforgeeks.org/c-sharp-union-of-two-hashset/](https://www.geeksforgeeks.org/c-sharp-union-of-two-hashset/)

一个 **HashSet** 是一个独特元素的无序集合。它属于*体系。集合.通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。对于两个 HashSet 的联盟， **HashSet <t>。使用 UnionWith(IEnumerable <t>)方法</t></t>** 。

**语法:**

```cs
firstSet.UnionWith(secondSet)
```

**异常:**如果*设置*为*空*，则此方法给出*参数空异常*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to find Union of two HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting even numbers less than
        // equal to 10 in HashSet mySet1
        for (int i = 0; i < 5; i++) {
            mySet1.Add(i * 2);
        }

        // Inserting odd numbers less than
        // equal to 10 in HashSet mySet2
        for (int i = 0; i < 5; i++) {
            mySet1.Add(i * 2 + 1);
        }

        // Creating a new HashSet that contains
        // the union of both the HashSet mySet1 & mySet2
        HashSet<int> ans = new HashSet<int>(mySet1);

        ans.UnionWith(mySet2);

        // Printing the union of both the HashSet
        foreach(int i in ans)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
0
2
4
6
8
1
3
5
7
9

```

**例 2:**

```cs
// C# code to find Union of two HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet1 = new HashSet<string>();

        // Creating a HashSet of strings
        HashSet<string> mySet2 = new HashSet<string>();

        // Inserting elements in mySet1
        mySet1.Add("Hello");
        mySet1.Add("GeeksforGeeks");
        mySet1.Add("GeeksforGeeks");

        // Inserting elements in mySet2
        mySet2.Add("You");
        mySet2.Add("are");
        mySet2.Add("the");
        mySet2.Add("best");

        // Creating a new HashSet that contains
        // the union of both the HashSet mySet1 & mySet2
        HashSet<string> ans = new HashSet<string>(mySet1);

        ans.UnionWith(mySet2);

        // Printing the union of both the HashSet
        foreach(string i in ans)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
Hello
GeeksforGeeks
You
are
the
best

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . union with？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.unionwith?view=netframework-4.7.2)