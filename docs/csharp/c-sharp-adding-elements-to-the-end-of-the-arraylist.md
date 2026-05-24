# C# |在数组列表末尾添加元素

> 原文:[https://www . geesforgeks . org/c-sharp-将元素添加到数组末尾列表/](https://www.geeksforgeeks.org/c-sharp-adding-elements-to-the-end-of-the-arraylist/)

**AddRange(ICollection)方法**用于将 ICollection 的元素添加到数组列表的末尾。或者换句话说，这个方法用于将其他集合中的多个元素添加到数组列表中。在这里，元素被定义为基元或非基元类型。

**语法:**

```cs
public virtual void AddRange (ICollection col);
```

这里，*列*是一个 ICollection，它的元素应该被添加到数组列表的末尾。集合本身不能为 null，但它可以包含 null 元素。

例外:

*   如果*列*的值为空，则该方法将给出**参数空异常**。
*   如果数组列表是只读的，或者数组列表有固定的大小，这个方法将给出 **NotSupportedException**

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate the AddRange() Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // Creates and initializes a new ArrayList
        ArrayList mylist = new ArrayList();
        mylist.Add("C# ");
        mylist.Add("DSA ");
        mylist.Add("Java ");
        mylist.Add("CPP");

        // Creates and initializes a new Queue
        Queue mydata = new Queue();
        mydata.Enqueue("C ");
        mydata.Enqueue("Python ");
        mydata.Enqueue("HTML ");
        mydata.Enqueue("CSS ");
        mydata.Enqueue("JavaScript ");
        mydata.Enqueue("Ruby");

        // Displays the ArrayList and the Queue.
        Console.Write("The original ArrayList: ");
        Data(mylist);

        Console.Write("The original Queue: ");
        Data(mydata);

        // Copies the elements of the queue to the end of the ArrayList.
        mylist.AddRange(mydata);

        // Displays the new ArrayList.
        Console.Write("The new ArrayList is: ");
        Data(mylist);
    }

    // method to display the ArrayList
    // and Queue elements
    public static void Data(IEnumerable mylis)
    {
        foreach(string str in mylis)
            Console.Write("{0}", str);
        Console.WriteLine();
    }
}
```

**输出:**

```cs
The original ArrayList: C# DSA Java CPP
The original Queue: C Python HTML CSS JavaScript Ruby
The new ArrayList is: C# DSA Java CPPC Python HTML CSS JavaScript Ruby

```

**例 2:**

```cs
// C# program to illustrate 
// the AddRange() Method
using System;
using System.Collections;

public class GFG {

    // Main method
    public static void Main()
    {

        // Creates and initializes a new ArrayList.
        ArrayList mylist = new ArrayList();
        mylist.Add(5);
        mylist.Add(10);
        mylist.Add(15);
        mylist.Add(20);
        mylist.Add(25);

        // Creates and initializes a new ArrayList.
        ArrayList mydata = new ArrayList();
        mydata.Add(30);
        mydata.Add(35);
        mydata.Add(40);
        mydata.Add(45);
        mydata.Add(50);

        // Displays both ArrayList.
        Console.WriteLine("The ArrayList 1: ");
        foreach(int i in mylist)
        {
            Console.WriteLine(i);
        }
        Console.WriteLine("The ArrayList 2: ");
        foreach(int j in mydata)
        {
            Console.WriteLine(j);
        }

        // Copies the elements of the mydata
        // to the end of the mylist
        mylist.AddRange(mydata);

        // Displays the new ArrayList.
        Console.WriteLine("The new ArrayList is :");
        for (int k = 0; k < mylist.Count; k++)
            Console.WriteLine(mylist[k]);
    }
}
```

**输出:**

```cs
The ArrayList 1: 
5
10
15
20
25
The ArrayList 2: 
30
35
40
45
50
The new ArrayList is :
5
10
15
20
25
30
35
40
45
50

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . addrange？view = net framework-4 . 7 . 2 # System _ Collections _ ArrayList _ AddRange _ System _ Collections _ ICollection _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.addrange?view=netframework-4.7.2# System_Collections_ArrayList_AddRange_System_Collections_ICollection_)