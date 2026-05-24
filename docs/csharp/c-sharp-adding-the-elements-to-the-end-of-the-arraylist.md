# C# |将元素添加到数组列表的末尾

> 原文:[https://www . geeksforgeeks . org/c-sharp-将元素添加到数组末尾列表/](https://www.geeksforgeeks.org/c-sharp-adding-the-elements-to-the-end-of-the-arraylist/)

**数组列表。AddRange(ICollection)方法**用于将 ICollection 的元素添加到 ***[数组列表](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.addrange?view=netframework-4.7.2)*** 的末尾。

**语法:**

```cs
public virtual void AddRange (System.Collections.ICollection c);
```

这里， **c** 是应该将元素添加到数组列表末尾的 ICollection。集合本身不能是*空*，但是它可以包含*空*的元素。

**异常:**

*   **参数异常:**如果 *c* 为空
*   **notSupportDexception:**如果数组列表是只读的或者数组列表有固定的大小。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to add the elements of an
// ICollection to the end of the ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");
        myList.Add("E");
        myList.Add("F");

        Console.WriteLine("Before AddRange Method");
        Console.WriteLine();

        // displaying the item of myList
        foreach(String str in myList)
        {
            Console.WriteLine(str);
        }

        Console.WriteLine("\nAfter AddRange Method\n");

        // Here we are using AddRange method
        // Which adds the elements of myList
        // Collection in myList again i.e.
        // we have copied the whole myList
        // in it
        myList.AddRange(myList);

        // displaying the item of List
        foreach(String str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
Before AddRange Method

A
B
C
D
E
F

After AddRange Method

A
B
C
D
E
F
A
B
C
D
E
F

```

**例 2:**

```cs
// C# code to add the elements of an
// ICollection to the end of the ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // adding elements in myList
        myList.Add("Geeks");
        myList.Add("GFG");
        myList.Add("C#");
        myList.Add("Tutorials");

        Console.WriteLine("Before AddRange Method");
        Console.WriteLine();

        // displaying the item of myList
        foreach(String str in myList)
        {
            Console.WriteLine(str);
        }

        Console.WriteLine("\nAfter AddRange Method\n");

        // taking array of String
        string[] str_add = { "Collections",
                             "Generic",
                             "List" };

        // here we are adding the elements
        // of the str_add to the end of
        // the myList
        myList.AddRange(str_add);

        // displaying the item of List
        foreach(String str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
Before AddRange Method

Geeks
GFG
C#
Tutorials

After AddRange Method

Geeks
GFG
C#
Tutorials
Collections
Generic
List

```

**注:**

*   ArrayList 接受 null 作为有效值，并允许重复元素。
*   ICollection 中元素的顺序保留在数组列表中。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . addrange？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.addrange?view=netframework-4.7.2)