# C# |数组列表。插入范围()方法

> 原文:[https://www . geesforgeks . org/c-sharp-ArrayList-insert range-method/](https://www.geeksforgeeks.org/c-sharp-arraylist-insertrange-method/)

**数组列表。C# 中的 InsertRange(Int32，ICollection)方法**用于将集合中的元素插入到指定索引处的[数组列表](https://www.geeksforgeeks.org/arraylist-in-c-sharp/)中。也就是说，插入的元素属于一个集合(即队列等)。

**语法:**

```cs
public virtual void InsertRange (int index, ICollection element);
```

**参数:**

*   **索引**:是*索引*，新元素要插入的地方。
*   **元素**:是*集合*，其元素将被插入到*数组列表*中的指定索引处。

**注意:** *集合不能为空，但可以包含为空的元素。*

**异常:**

*   **参数空异常:**如果**元素**为空。
*   **argumentoutofrangerexception:**如果**指数**小于零或指数大于计数器。
*   **notSupportDexception:**如果数组列表是只读的或者数组列表具有固定的大小。

**例 1:**

```cs
// C# program to demonstrate the 
// ArrayList.InsertRange(Int32, 
// ICollection) Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {
        // initializes a new ArrayList
        ArrayList ArrList = new ArrayList();

        // adding values in the 
        // ArrayList using "Add"
        ArrList.Add("A");
        ArrList.Add("D");
        ArrList.Add("E");
        ArrList.Add("F");

        // initializes a new Stack
        // as collection
        Stack s = new Stack();

        // pushing values in the stack
        // values are pop as B, C
        s.Push("C");
        s.Push("B");

        // Displays the ArrayList and the Queue
        Console.WriteLine("The ArrayList initially has:");
        Display(ArrList);
        Console.WriteLine("The collection initially has:");
        Display(s);

        // Copies the elements of the stack 
        // to the ArrayList at index 1.
        ArrList.InsertRange(1, s);

        // Displays the ArrayList.
        Console.WriteLine("After insert the collection in the ArrList:");
        Display(ArrList);
    }

    // Display function
    public static void Display(IEnumerable ArrList)
    {
        foreach(Object a in ArrList)
        {
            Console.Write("   " + a);
        }
        Console.WriteLine();
    }
}
```

**Output:**

```cs
The ArrayList initially has:
   A   D   E   F
The collection initially has:
   B   C
After insert the collection in the ArrList:
   A   B   C   D   E   F

```

**例 2:** +

```cs
// C# program to demonstrate the 
// ArrayList.InsertRange(Int32, 
// ICollection) Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {
        // initializes a new ArrayList
        ArrayList ArrList = new ArrayList();

        // adding values in the ArrayList
        // using "Insert" method
        ArrList.Insert(0, "A");
        ArrList.Insert(1, "D");
        ArrList.Insert(2, "E");
        ArrList.Insert(3, "G");

        // Initializes a new Stack
        // as collection
        Stack s = new Stack();

        // pushing values in the stack
        // values are pop as B, C
        s.Push("C");
        s.Push("B");

        // Displays the ArrayList and the Queue.
        Console.WriteLine("The ArrayList initially has:");
        Display(ArrList);
        Console.WriteLine("The collection initially has:");
        Display(s);

        // Copies the elements of the stack 
        // to the ArrayList at index 1.
        ArrList.InsertRange(1, s);

        // Displays the ArrayList.
        Console.WriteLine("After insert the collection in the ArrList:");
        Display(ArrList);

        // insert F by finding the index of G
        // using IndexOf() method
        ArrList.Insert(ArrList.IndexOf("G"), "F");
        Console.WriteLine("After inserting F before G:");
        Display(ArrList);
    }

    // Display function
    public static void Display(IEnumerable ArrList)
    {
        foreach(Object a in ArrList)
        {
            Console.Write(" " + a);
        }
        Console.WriteLine();
    }
}
```

**Output:**

```cs
The ArrayList initially has:
 A D E G
The collection initially has:
 B C
After insert the collection in the ArrList:
 A B C D E G
After inserting F before G:
 A B C D E F G

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . insert range？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.insertrange?view=netframework-4.8)