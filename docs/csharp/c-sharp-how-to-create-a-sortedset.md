# C# |如何创建排序集

> 原文:[https://www . geesforgeks . org/c-sharp-how-create-a-sorted set/](https://www.geeksforgeeks.org/c-sharp-how-to-create-a-sortedset/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
SortedSet<T> mySortedSet = new SortedSet<T>();

```

这里 *mySortedSet* 是 SortedSet 的名称， *T* 是类型参数。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to create a SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // Adding elements in mySortedSet
        for (int i = 1; i <= 6; i++) {
            mySortedSet.Add(2 * i + 1);
        }

        // Displaying elements in mySortedSet
        Console.WriteLine("The elements in mySortedSet are : ");

        // Displaying the element in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The elements in mySortedSet are : 
3
5
7
9
11
13

```

**例 2:**

```cs
// C# code to create a SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet = new SortedSet<string>();

        // Adding elements in mySortedSet
        mySortedSet.Add("H");
        mySortedSet.Add("E");
        mySortedSet.Add("L");
        mySortedSet.Add("L");
        mySortedSet.Add("O");

        // Displaying elements in mySortedSet
        Console.WriteLine("The elements in mySortedSet are : ");

        // Displaying the element in mySortedSet
        foreach(string str in mySortedSet)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
The elements in mySortedSet are : 
E
H
L
O

```