# C# |两个 HashSets 的交集

> 原文:[https://www . geesforgeks . org/c-sharp-两两相交-hashsets/](https://www.geeksforgeeks.org/c-sharp-intersection-of-two-hashsets/)

一个 **HashSet** 是一个独特元素的无序集合。见于 ***系统。集合.**通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet <t>。intersecwith(IEnumerable<t>)方法</t></t>** 用于修改当前 *HashSet* 对象，使其只包含该对象和指定集合中存在的元素。

**语法:**

```cs
mySet1.IntersectWith(mySet2)
```

这里*我自己 1* 和*我自己 2* 是两个 HashSets。

**异常:**如果哈希表为*空*，该方法将给出*参数异常*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to find Intersection 
//of two HashSets
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
        Console.WriteLine("Elements in Set 1 :");

        for (int i = 0; i < 5; i++) {
            mySet1.Add(i * 2);
            Console.WriteLine(i * 2);
        }

        // Inserting odd numbers less than
        // equal to 10 in HashSet mySet2
        Console.WriteLine("Elements in Set 2 : ");
        for (int i = 0; i < 5; i++) {
            mySet1.Add(i * 2 + 1);
            Console.WriteLine(i *2 + 1);
        }

        // Creating a new HashSet that contains
        // the Intersection of both the HashSet mySet1 & mySet2
        HashSet<int> ans = new HashSet<int>(mySet1);

        ans.IntersectWith(mySet2);

        // Printing the Intersection of both the HashSets
        // It should show no element in the output
        // as there is no element common in both
        // the HashSets
        foreach(int i in ans)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
Elements in Set 1 :
0
2
4
6
8
Elements in Set 2 : 
1
3
5
7
9

```

**例 2:**

```cs
// C# code to find Intersection
// of two HashSets
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
        mySet1.Add("Geeks");
        mySet1.Add("GeeksforGeeks");

        // Inserting elements in mySet2
        mySet2.Add("Geeks");
        mySet2.Add("and");
        mySet2.Add("GeeksforGeeks");
        mySet2.Add("are");
        mySet2.Add("the");
        mySet2.Add("best");

        // Creating a new HashSet that contains
        // the Intersection of both the HashSet mySet1 & mySet2
        HashSet<string> ans = new HashSet<string>(mySet1);

        ans.IntersectWith(mySet2);

        // Printing the Intersection of both the HashSet
        foreach(string i in ans)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
Geeks
GeeksforGeeks

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . intersecwit？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.intersectwith?view=netframework-4.7.2)