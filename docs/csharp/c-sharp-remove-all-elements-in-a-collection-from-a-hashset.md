# C# |从哈希集中移除集合中的所有元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-all-elements-in-a-collection-from-hashset/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-in-a-collection-from-a-hashset/)

一个 **HashSet** 是一个独特元素的无序集合。见于 ***系统。集合.**通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet <t>。ExceptWith(IEnumerable <t>)方法</t></t>** 用于从当前 *HashSet* 对象中移除指定集合中的所有元素。

**语法:**

```cs
mySet2.ExceptWith(mySet1)

```

这里，*my STAT1*和*my stat2*是两个 HashSets，函数返回不在 my STAT1 中的 my stat2 元素。

**异常:**如果哈希表为*空*，该方法将给出*参数异常*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove all elements
// in a collection from a HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Inserting elements into HashSet mySet1
        for (int i = 0; i < 7; i++) {
            mySet1.Add(i);
        }

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements into HashSet mySet2
        for (int i = 4; i < 11; i++) {
            mySet2.Add(i);
        }

        // Removing all elements in a collection from a HashSet
        mySet2.ExceptWith(mySet1);

        // Printing the elements in mySet2
        // It only prints the elements which are
        // in mySet2 and not in mySet1
        foreach(int i in mySet2)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
7
8
9
10

```

**例 2:**

```cs
// C# code to remove all elements
// in a collection from a HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet1 = new HashSet<string>();

        // Inserting elements into HashSet mySet1
        mySet1.Add("Punjab");
        mySet1.Add("Haryana");
        mySet1.Add("Jammu");
        mySet1.Add("Himachal");
        mySet1.Add("Delhi");

        // Displaying all elements in mySet1
        Console.WriteLine("The elements in mySet1 are : ");

        foreach(string i in mySet1)
        {
            Console.WriteLine(i);
        }

        // Creating a HashSet of strings
        HashSet<string> mySet2 = new HashSet<string>();

        // Inserting elements into HashSet mySet2
        mySet2.Add("Bangalore");
        mySet2.Add("Kerala");
        mySet2.Add("Uttar Pradesh");
        mySet2.Add("Himachal");
        mySet2.Add("Delhi");

        // Displaying all elements in mySet2
        Console.WriteLine("The elements in mySet2 are : ");

        foreach(string i in mySet2)
        {
            Console.WriteLine(i);
        }

        // Removing all elements in a collection from a HashSet
        mySet2.ExceptWith(mySet1);

        // Printing the elements in mySet2
        // It only prints the elements which are
        // in mySet2 and not in mySet1

        Console.WriteLine("The elements in mySet2 are : ");

        foreach(string i in mySet2)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The elements in mySet1 are : 
Punjab
Haryana
Jammu
Himachal
Delhi
The elements in mySet2 are : 
Bangalore
Kerala
Uttar Pradesh
Himachal
Delhi
The elements in mySet2 are : 
Bangalore
Kerala
Uttar Pradesh

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . except with？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.exceptwith?view=netframework-4.7.2)