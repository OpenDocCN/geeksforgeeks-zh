# C# |创建具有指定初始容量的数组列表

> 原文:[https://www . geeksforgeeks . org/c-sharp-creating-ArrayList-having-specified-initial-capacity/](https://www.geeksforgeeks.org/c-sharp-creating-an-arraylist-having-specified-initial-capacity/)

**ArrayList(Int32)构造函数**用于初始化 ArrayList 类的一个新实例，该实例将为空，并将具有指定的初始容量。[数组列表](https://www.geeksforgeeks.org/arraylist-in-c-sharp/)表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。

> **语法:**公共数组列表(int 容量)；
> 
> 这里，*容量*是新列表最初可以存储的元素数量。
> 
> **异常:**如果容量小于零，这将给出*argumentout of range Exception*。

**要点:**

*   数组列表可以容纳的元素数量被称为数组列表的[容量](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-that-the-arraylist-can-contain/)。如果元素将被添加到数组列表中，那么容量将通过重新分配内部数组而自动增加。
*   如果可以估计集合的大小，指定初始容量将消除在向数组列表添加元素时执行大量调整大小操作的要求。
*   这个构造函数是一个 O(n)运算，其中 n 是容量。

下面的程序说明了上述构造函数的使用:

**例 1:**

```cs
// C# Program to illustrate how
// to create a ArrayList having
// specified initial capacity
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // arrlist is the ArrayList object
        // ArrayList(10) is the constructor
        // used to initializes a new
        // instance of the ArrayList class
        // having 10 as capacity
        ArrayList arrlist = new ArrayList(10);

        Console.Write("Number of elements: ");

        // Count property is used to get the
        // number of elements in ArrayList
        // It will give 0 as no elements 
        // are present
        Console.WriteLine(arrlist.Count);

        Console.Write("Capacity of ArrayList: ");

        // using capacity property
        Console.WriteLine(arrlist.Capacity);

        // inserting elements to ArrayList
        arrlist.Add("C");
        arrlist.Add("C++");
        arrlist.Add("Java");
        arrlist.Add("C#");

        Console.Write("Number of elements: ");

        // Count property is used to get the
        // number of elements in ArrayList
        Console.WriteLine(arrlist.Count);

        Console.Write("Capacity of ArrayList: ");

        // using capacity property
        Console.WriteLine(arrlist.Capacity);
    }
}
```

**输出:**

```cs
Number of elements: 0
Capacity of ArrayList: 10
Number of elements: 4
Capacity of ArrayList: 10

```

**例 2:** 为*argumentout of range exception*

```cs
// C# Program to illustrate how
// to create a ArrayList having
// specified initial capacity
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // arrlist is the ArrayList object
        // taking capacity less than zero
        ArrayList arrlist = new ArrayList(-4);

        // using capacity property
        Console.WriteLine(arrlist.Capacity);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:“容量”必须是非负数。
> 参数名称:容量

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList-ctor？view = net framework-4 . 7 . 2 # System _ Collections _ ArrayList _ _ ctor _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.-ctor?view=netframework-4.7.2# System_Collections_ArrayList__ctor_System_Int32_)