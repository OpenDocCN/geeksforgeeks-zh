# C# |从哈希集中删除指定的元素

> 原文:[https://www . geesforgeks . org/c-sharp-从 a-hashset 中移除指定元素/](https://www.geeksforgeeks.org/c-sharp-remove-the-specified-element-from-a-hashset/)

一个 **HashSet** 是一个独特元素的无序集合。它属于*T3 系统。集合.通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet < T >。移除(T)方法**用于从 HashSet < T >对象中移除指定元素。

**语法:**

```cs
public bool Remove (T item);

```

这里，**项**是要删除的元素。

**返回值:**如果成功找到并移除元素，则该方法返回*真*，如果在 HashSet < **T** >对象中未找到项目，则返回*假*。

下面的例子说明了 **HashSet <t>的使用。</t>解除(T)法**:

**例 1:**

```cs
// C# code to remove the specified 
// element from a HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // Inserting even numbers less than
        // equal to 20 in HashSet mySet
        for (int i = 0; i < 10; i++) {
            mySet.Add(i * 2);
        }

        Console.WriteLine("The elements in HashSet are : ");

        // Displaying the elements in HashSet
        foreach(int i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in HashSet
        Console.WriteLine("Number of elements are : " + mySet.Count);

        // Removing the element 10 if present
        if (mySet.Contains(10)) {
            mySet.Remove(10);
        }

        Console.WriteLine("The elements in HashSet are : ");

        // Displaying the elements in HashSet
        foreach(int i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in HashSet
        Console.WriteLine("Number of elements are : " + mySet.Count);
    }
}
```

**Output:**

```cs
The elements in HashSet are : 
0
2
4
6
8
10
12
14
16
18
Number of elements are : 10
The elements in HashSet are : 
0
2
4
6
8
12
14
16
18
Number of elements are : 9

```

**例 2:**

```cs
// C# code to remove the specified
//  element from a HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet = new HashSet<string>();

        // Inserting elements into HashSet
        mySet.Add("Data Structures");
        mySet.Add("Algorithms");
        mySet.Add("Java");
        mySet.Add("Puzzles");
        mySet.Add("Coding");

        Console.WriteLine("The elements in HashSet are : ");

        // Displaying the elements in HashSet
        foreach(string i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in HashSet
        Console.WriteLine("Number of elements are : " + mySet.Count);

        // Removing the element "JavaScript" if present
        if (mySet.Contains("JavaScript")) {
            mySet.Remove("JavaScript");
        }

        Console.WriteLine("The elements in HashSet are : ");

        // Displaying the elements in HashSet
        foreach(string i in mySet)
        {
            Console.WriteLine(i);
        }

        // Displaying the number of elements in HashSet
        Console.WriteLine("Number of elements are : " + mySet.Count);
    }
}
```

**Output:**

```cs
The elements in HashSet are : 
Data Structures
Algorithms
Java
Puzzles
Coding
Number of elements are : 5
The elements in HashSet are : 
Data Structures
Algorithms
Java
Puzzles
Coding
Number of elements are : 5

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.remove?view=netframework-4.7.2)