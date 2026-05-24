# C# | 数组列表。InsertRange()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-arraylist-insertrange-method/](https://www.geeksforgeeks.org/c-sharp-arraylist-insertrange-method/)

## `ArrayList.InsertRange(Int32, ICollection)` 方法

`ArrayList.InsertRange(Int32, ICollection)` 方法用于将集合中的元素插入到指定索引处的 `ArrayList` 中。也就是说，插入的元素属于一个集合（即队列等）。

### 语法:

```cs
public virtual void InsertRange (int index, ICollection element);
```

### 参数:

*   `index`: 是*索引*，新元素要插入的地方。
*   `element`: 是*集合*，其元素将被插入到 `ArrayList` 中的指定索引处。

**注意:** `集合`不能为空，但可以包含为空的元素。

### 异常:

*   `ArgumentNullException`: 如果 `element` 为空。
*   `ArgumentOutOfRangeException`: 如果 `index` 小于零或 `index` 大于 `Count`。
*   `NotSupportedException`: 如果 `ArrayList` 是只读的或者 `ArrayList` 具有固定的大小。

### 例 1:

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
            Console.Write("   " + a);
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

### 例 2:

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

### 参考:

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.insertrange?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.insertrange?view=netframework-4.8)