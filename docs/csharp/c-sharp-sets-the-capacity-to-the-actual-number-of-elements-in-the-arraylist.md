# C# |将容量设置为数组列表中元素的实际数量

> 原文:[https://www . geeksforgeeks . org/c-sharp-将数组列表中元素的容量设置为实际数量/](https://www.geeksforgeeks.org/c-sharp-sets-the-capacity-to-the-actual-number-of-elements-in-the-arraylist/)

**数组列表。TrimToSize 方法**用于将容量设置为数组列表中元素的实际数量。如果没有新元素添加到集合中，它可以用来最小化集合的内存开销。

**注:**此方法为 O(n)运算，其中 n 为[计数](https://www.geeksforgeeks.org/c-get-the-number-of-elements-actually-contained-in-the-arraylist/)。

**语法:**

```cs
public virtual void TrimToSize ();
```

**异常:**如果[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)是只读的或者有固定的大小，这个方法将给出 **NotSupportedException** 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate the TrimToSize() Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // create and initialize new ArrayList
        ArrayList mylist = new ArrayList();
        mylist.Add("Geeks");
        mylist.Add("GFG");
        mylist.Add("DSA");
        mylist.Add("C#");
        mylist.Add("Java");
        mylist.Add("C++");

        // Capacity of ArrayList before trimmimg
        Console.WriteLine("Before trimming the capacity is: {0}",
                                                mylist.Capacity);

        // trim the ArrayList
        mylist.TrimToSize();

        // Capacity of ArrayList after trimming
        Console.WriteLine("After trimming the capacity is: {0}",
                                               mylist.Capacity);
    }
}
```

**输出:**

```cs
Before trimming the capacity is: 8
After trimming the capacity is: 6

```

**例 2:**

```cs
// C# program to illustrate the TrimToSize() Method
using System;
using System.Collections;

class GFG {

   // Main Method
   public static void Main()  {

      // Creating and initializing a new ArrayList.
      ArrayList mylist = new ArrayList();
      mylist.Add("C# ");
      mylist.Add("Java ");
      mylist.Add("C++ ");
      mylist.Add("DSA ");
      mylist.Add("Python ");
      mylist.Add("Web");

      // Displaying the count, capacity 
      // and values of the ArrayList.
      Console.WriteLine("Before Using TrimToSize Method:");
      Console.WriteLine("Count: {0}", mylist.Count);
      Console.WriteLine("Capacity: {0}", mylist.Capacity);
      Console.Write("Values are: ");
      Display(mylist);

      Console.WriteLine();

      // Trim the ArrayList.
      mylist.TrimToSize();

      // Displaying the count, capacity 
      // and values of the ArrayList.
      Console.WriteLine("After Using TrimToSize Method:");
      Console.WriteLine("Count: {0}", mylist.Count);
      Console.WriteLine("Capacity: {0}", mylist.Capacity);
      Console.Write("Values are: ");
      Display(mylist);

      // Clear the ArrayList.
      mylist.Clear();

      Console.WriteLine();

      // Displaying the count, capacity 
      // and values of the ArrayList.
      Console.WriteLine("After Using Clear Method:");
      Console.WriteLine("Count: {0}", mylist.Count);
      Console.WriteLine("Capacity: {0}", mylist.Capacity);
      Console.Write("Values are: ");
      Display(mylist);

      // again trim the ArrayList
      mylist.TrimToSize();

      Console.WriteLine();

      // Displaying the count, capacity 
      // and values of the ArrayList.
      Console.WriteLine("After Again Using TrimToSize Method:");
      Console.WriteLine("Count: {0}", mylist.Count);
      Console.WriteLine("Capacity: {0}", mylist.Capacity);
      Console.Write("Values are: ");
      Display(mylist);
   }

   // to display the values of ArrayList
   public static void Display(IEnumerable ienum)
   {
      foreach (Object ob in ienum)
         Console.Write("{0}", ob);

      Console.WriteLine();
   }

}
```

**输出:**

```cs
Before Using TrimToSize Method:
Count: 6
Capacity: 8
Values are: C# Java C++ DSA Python Web

After Using TrimToSize Method:
Count: 6
Capacity: 6
Values are: C# Java C++ DSA Python Web

After Using Clear Method:
Count: 0
Capacity: 6
Values are: 

After Again Using TrimToSize Method:
Count: 0
Capacity: 4
Values are: 

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . trimtosize？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.trimtosize?view=netframework-4.7.2)