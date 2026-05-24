# C# |检查数组是否同步(线程安全)

> 原文:[https://www . geesforgeks . org/c-sharp-检查数组是否同步-线程安全与否/](https://www.geeksforgeeks.org/c-sharp-check-if-an-array-is-synchronized-thread-safe-or-not/)

**阵列。IsSynchronized Property** 用于获取一个值，该值指示对[数组](https://www.geeksforgeeks.org/c-array-class/)的访问是否同步(线程安全)。

**语法:**

```cs
public bool IsSynchronized { get; }
```

**属性值:**对于所有数组，该属性始终返回 *false* 。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# program to illustrate
// IsSynchronized Property of
// Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // The array with dimensions  
        // specified 4 row and 2 column. 
        int[, ] arr = new int[4, 2] {{1, 2 }, {3, 4},  
                                            {5, 6 }, {7, 8}};

        // Here we check whether the
        // array is synchronized (thread safe)
        // or not
        Console.WriteLine("Result: " + arr.IsSynchronized);
    }
}
}
```

**Output:**

```cs
Result: False

```

**例 2:**

```cs
// C# program to illustrate
// IsSynchronized Property of
// Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string.
        string[] topic;

        // allocating null to array
        topic = new string[] { null };

        // Here we check whether the
        // array is synchronized (thread safe)
        // or not
        Console.WriteLine("Result: " + topic.IsSynchronized);
    }
}
}
```

**Output:**

```cs
Result: False

```

**注:**

*   [数组](https://www.geeksforgeeks.org/c-array-class/)实现[同步](https://docs.microsoft.com/en-us/dotnet/api/system.array.issynchronized?view=netframework-4.7.2)属性，因为*系统需要它。收藏。收藏*界面。
*   使用[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)的类也可以使用同步根属性实现自己的同步。
*   枚举集合不是线程安全的过程。即使同步了集合，其他线程仍然可以修改集合，这将导致枚举数引发异常。为了保证枚举期间的线程安全，可以在整个枚举期间锁定集合，也可以捕获由其他线程所做的更改导致的异常。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.issynchronized?view=netframework-4.7.2)