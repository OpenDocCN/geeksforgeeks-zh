# 如何在 C# 中创建七元组或七元组？

> 原文:[https://www . geeksforgeeks . org/如何创建 7 元组或 c-sharp 中的七元组/](https://www.geeksforgeeks.org/how-to-create-7-tuple-or-septuple-in-c-sharp/)

在 C# 中，7 元组是包含 7 个元素的[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，也称为**七元组**。您可以使用两种不同的方法创建一个 7 元组:

*   **[使用元组< T1、T2、T3、T4、T5、T6、T7 > (T1、T2、T3、T4、T5、T6、T7)构造器](# Using Tuple<T1,T2,T3,T4,T5,T6,T7>(T1, T2, T3, T4, T5, T6, T7) Constructor)**
*   **[使用创建方法](# Using the Create method)**

### **使用元组< T1、T2、T3、T4、T5、T6、T7 > (T1、T2、T3、T4、T5、T6、T7)构造器**

**您可以使用元组 <t1 t2="" t3="" t4="" t5="" t6="" t7="">(T1、T2、T3、T4、T5、T6、T7)构造器创建 7 元组。它初始化元组<t1 t2="" t3="" t4="" t5="" t6="" t7="">类的一个新实例。但是当你使用这个构造函数创建一个元组时，那么*你必须指定存储在元组中的元素*的类型。</t1></t1>**

****语法:****

```cs
public Tuple (T1 item1, T2 item2, T3 item3, T4 item4, T5 item5, T6 item6, T7 item7);
```

****参数:****

*   ****item1:** 是第一个元组成分的值。**
*   ****item2:** 是第二元组分量的值。**
*   ****item3:** 是第三元组分量的值。**
*   ****item4:** 是第四元组分量的值。**
*   ****item5:** 是第五元组分量的值。**
*   ****item6:** 是第六元组分量的值。**
*   ****item7:** 是第七元组分量的值。**

****示例:****

```cs
// C# program to create 7-tuple
// using the tuple constructor
using System;
public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with seven elements
        // Using Tuple<T1, T2, T3, T4, T5, T6,
        // T7>(T1, T2, T3, T4, T5, T6, T7) 
        // constructor
        Tuple<int, int, int, int, int, int, int> My_Tuple = new Tuple<int,
               int, int, int, int, int, int>(22, 33, 44, 545, 55, 88, 66);

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
        Console.WriteLine("Element 4: " + My_Tuple.Item4);
        Console.WriteLine("Element 5: " + My_Tuple.Item5);
        Console.WriteLine("Element 6: " + My_Tuple.Item6);
        Console.WriteLine("Element 7: " + My_Tuple.Item7);
    }
}
```

****Output:**

```cs
Element 1: 22
Element 2: 33
Element 3: 44
Element 4: 545
Element 5: 55
Element 6: 88
Element 7: 66

```** 

### **使用创建方法**

**您也可以在 create 方法的帮助下创建 7 元组。当你使用这个方法时，那么*就不需要指定存储在元组中的元素的类型*。**

****语法:****

> **公共静态元组<t1>创建 <t1 t2="" t3="" t4="" t5="" t6="" t7="">(T1 项 1、T2 项 2、T3 项 3、T4 项 4、T5 项 5、T6 项 6、T7 项 7)；</t1></t1>**

****类型参数:****

*   ****T1:** 是第一个元组成分的类型。**
*   ****T2:** 是第二元组成分的类型。**
*   ****T3:** 是三元组成分的类型。**
*   ****T4:** 是第四元组成分的类型。**
*   ****T5:** 是第五元组成分的类型。**
*   ****T6:** 是第六元组成分的类型。**
*   ****T7:** 是第七元组成分的类型。**

****参数:****

*   ****item1:** 是第一个元组成分的值。**
*   ****item2:** 是第二元组分量的值。**
*   ****item3:** 是第三元组分量的值。**
*   ****item4:** 是第四元组分量的值。**
*   ****item5:** 是第五元组分量的值。**
*   ****item6:** 是第六元组分量的值。**
*   ****item7:** 是第七元组分量的值。**

****返回类型:**该方法返回 7 元组，其值为*项 1、*项 2、、*项 3* 、*项 4* 、*项 5* 、*项 6* 和*项 7* 。**

****示例:****

```cs
// C# program to create 7-tuple
// using create method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with seven 
        // elements Using Create method
        var My_Tuple = Tuple.Create("C", "C++", "Ruby",
                      "Java", "Perl", "PHP", "Python");

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
        Console.WriteLine("Element 4: " + My_Tuple.Item4);
        Console.WriteLine("Element 5: " + My_Tuple.Item5);
        Console.WriteLine("Element 6: " + My_Tuple.Item6);
        Console.WriteLine("Element 7: " + My_Tuple.Item7);
    }
}
```

****Output:**

```cs
Element 1: C
Element 2: C++
Element 3: Ruby
Element 4: Java
Element 5: Perl
Element 6: PHP
Element 7: Python

```** 

****参考:****

*   **[https://docs.microsoft.com/en-us/dotnet/api/system.tuple-7.-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-7.-ctor?view=netframework-4.8)**
*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . tuple . create？view = net framework-4.8 # System _ Tuple _ Create _ _ 7 _ _ 0 _ _ 1 _ _ 2 _ _ 3 _ _ 4 _ _ 5 _ _ 6 _](https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8# System_Tuple_Create__7___0___1___2___3___4___5___6_)**