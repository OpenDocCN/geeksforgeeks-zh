# C# |在数组列表

中的一系列元素上复制集合的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-数组列表中元素范围上的元素集合副本/](https://www.geeksforgeeks.org/c-sharp-copy-the-elements-of-collection-over-a-range-of-elements-in-arraylist/)

**数组列表。SetRange(Int32，ICollection)方法**用于将集合的元素复制到数组列表中的一系列元素上。

**语法:**

```cs
public virtual void SetRange (int index, System.Collections.ICollection c);
```

**参数:**

> **索引:**是从零开始的数组列表索引，从这里开始复制 *c* 的元素。该参数的类型为*系统。Int32* 。
> 
> **c:** 这是一个[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)，其元素要复制到数组列表中。集合本身不能为空，但它可以包含为空的元素。

**异常:**

*   **参数空异常:**如果 *c* 的值为空。
*   **notSupportDexception:**如果数组列表是只读的。
*   **argumentoutofrangerexception:**如果指数*小于零*或*【指数+c 中元素个数】>计数*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# Program to illustrate the 
// SetRange() Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // Create and initialize ArrayList
        ArrayList mylist = new ArrayList();
        mylist.Add("G");
        mylist.Add("e");
        mylist.Add("e");
        mylist.Add("k");
        mylist.Add("s");
        mylist.Add("G");
        mylist.Add("F");
        mylist.Add("G");

        // There are total 4 elements
        string[] str = { "This", "is", "C#", "Tutorial" };

        // using SetRange() Method
        // starting from index 0
        mylist.SetRange(0, str);

        Show("ArrayList is", mylist);
    }

    // show method to display the result
    static void Show(string arr, ArrayList mylist)
    {
        for (int j = 0; j < mylist.Count; j++) {

            Console.WriteLine(arr + "[" + j + "] = " + mylist[j]);
        }
    }
}
```

**Output:**

```cs
ArrayList is[0] = This
ArrayList is[1] = is
ArrayList is[2] = C#
ArrayList is[3] = Tutorial
ArrayList is[4] = s
ArrayList is[5] = G
ArrayList is[6] = F
ArrayList is[7] = G

```

**例 2:**

```cs
// C# Program to illustrate the 
// SetRange() Method
using System;
using System.Collections;

class GFG {
    // Main method
    public static void Main()
    {
        // Create and initialize ArrayList
        ArrayList mylist1 = new ArrayList();
        mylist1.Add("Hello ");
        mylist1.Add("Welcome ");
        mylist1.Add("to ");
        mylist1.Add("online ");
        mylist1.Add("portal ");
        mylist1.Add("of ");
        mylist1.Add("Geeks ");
        mylist1.Add("for ");
        mylist1.Add("Geeks ");

        // Create and initialize new ArrayList
        ArrayList mylist2 = new ArrayList();
        mylist2.Add("This ");
        mylist2.Add("is ");
        mylist2.Add("C# ");
        mylist2.Add("tutorial");
        mylist2.Add(".");

        // Displays the values of 6 
        // elements of mylist1 starting
        // at index 0.
        ArrayList result = mylist1.GetRange(0, 6);

        Console.WriteLine("String from index number 0 to 6:");
        {
            foreach(Object obj in result)
                Console.Write("{0}", obj);
            Console.WriteLine();
        }

        // Replace the value of 5 element
        // starting from index 1
        // with the values in mylist2
        mylist1.SetRange(1, mylist2);

        // Display the result
        result = mylist1.GetRange(0, 6);
        Console.WriteLine("After SetRange() Method:");
        {
            foreach(Object obj in result)
                Console.Write("{0}", obj);
            Console.WriteLine();
        }
    }
}
```

**Output:**

```cs
String from index number 0 to 6:
Hello Welcome to online portal of 
After SetRange() Method:
Hello This is C# tutorial.

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . set range？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.setrange?view=netframework-4.7.2)