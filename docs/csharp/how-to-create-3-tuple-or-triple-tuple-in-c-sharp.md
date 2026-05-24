# 如何在 C# 中创建三元组或三元组？

> 原文:[https://www . geeksforgeeks . org/如何在 c-sharp 中创建三元组或三元组/](https://www.geeksforgeeks.org/how-to-create-3-tuple-or-triple-tuple-in-c-sharp/)

在 C# 中，一个 3 元组是一个包含三个元素的[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，它也被称为**三元组**。您可以使用两种不同的方法创建三元组:

*   **[使用元组< T1、T2、T3 > (T1、T2、T3)构造器](# Using Tuple<T1,T2,T3>(T1, T2, T3) Constructor)**
*   **[使用创建方法](# Using the Create method)**

### **使用元组< T1，T2，T3 > (T1，T2，T3)构造器**

**您可以使用元组 <t1 t2="">(T1，T2，T3)构造器创建 3 元组。它初始化元组<t1 t2="" t3="">类的一个新实例。但是当你使用这个构造函数创建一个元组时，那么*你必须指定存储在元组中的元素*的类型。</t1></t1>**

****语法:****

```cs
public Tuple (T1 item1, T2 item2, T3 item3);
```

****参数:****

*   ****item1:** 是第一个元组成分的值。**
*   ****item2:** 是第二元组分量的值。**
*   ****item3:** 是第三元组分量的值。**

****示例:****

```cs
// C# program to create 3-tuple
// using the tuple constructor
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with three elements
        // Using Tuple<T1, T2, T3>(T1, T2, T3) constructor
        Tuple<string, int, char> My_Tuple = new Tuple<string, int, char>("GeeksforGeeks", 10, 'C#');

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
    }
}
```

****Output:**

```cs
Element 1: GeeksforGeeks
Element 2: 10
Element 3: C#

```** 

### **使用创建方法**

**您也可以借助 create 方法创建三元组。当你使用这个方法时，那么*就不需要指定存储在元组中的元素的类型*。**

****语法:****

```cs
public static Tuple<T1,T2,T3> Create<T1, T2, T3> (T1 item1, T2 item2, T3 item3);
```

****类型参数:****

*   ****T1:** 是第一个元组成分的类型。**
*   ****T2:** 是第二元组成分的类型。**
*   ****T3:** 是三元组成分的类型。**

****参数:****

*   ****item1:** 是第一个元组成分的值。**
*   ****item2:** 是第二元组分量的值。**
*   ****item3:** 是第三元组分量的值。**

****返回类型:**该方法返回三元组，其值为*项 1、*项 2、项和*项 3* 。**

****示例:****

```cs
// C# program to create 3-tuple
// using create method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with three 
        // elements using Create method
        var My_Tuple = Tuple.Create("Geeks", 20, 'f');

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
    }
}
```

****Output:**

```cs
Element 1: Geeks
Element 2: 20
Element 3: f

```** 

****参考文献:****

*   **[https://docs.microsoft.com/en-us/dotnet/api/system.tuple-3.-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-3.-ctor?view=netframework-4.8)**
*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . tuple . create？view = net framework-4.8 # System _ Tuple _ Create _ _ 3 _ _ 0 _ _ 1 _ _ 2 _](https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8# System_Tuple_Create__3___0___1___2_)**