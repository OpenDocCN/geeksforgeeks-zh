# C# |从另一个集合创建 HashSet】

> 原文:[https://www . geesforgeks . org/c-sharp-create-hashset-from-other-collection/](https://www.geeksforgeeks.org/c-sharp-create-hashset-from-another-collection/)

一个 **HashSet** 是一个独特元素的无序集合。它属于*T3 系统。集合.通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。您可以从另一个集合创建一个 HashSet，方法是在创建 HashSet 的对象时将该集合作为参数传递。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Create HashSet
// from another collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // Inserting even numbers less than
        // equal to 10 in HashSet mySet
        for (int i = 0; i < 5; i++) {
            mySet.Add(i * 2);
        }

        // Creating new HashSet mySet_new from already
        // Created HashSet mySet
        HashSet<int> mySet_new = new HashSet<int>(mySet);

        Console.WriteLine("The elements in newly created HashSet are : ");

        // Displaying the elements of newly created HashSet
        foreach(int i in mySet_new)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The elements in newly created HashSet are : 
0
2
4
6
8

```

**例 2:**

```cs
// C# code to Create HashSet
// from another collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet = new HashSet<string>();

        // Inserting elements into HashSet mySet
        mySet.Add("Delhi");
        mySet.Add("Noida");
        mySet.Add("Chandigarh");
        mySet.Add("New York");
        mySet.Add("Bangalore");

        // Creating new HashSet mySet_new from already
        // Created HashSet mySet
        HashSet<string> mySet_new = new HashSet<string>(mySet);

        Console.WriteLine("The elements in newly created HashSet are : ");

        // Displaying the elements of newly created HashSet
        foreach(string i in mySet_new)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The elements in newly created HashSet are : 
Delhi
Noida
Chandigarh
New York
Bangalore

```