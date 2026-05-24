# C# |元组类

> 原文:[https://www.geeksforgeeks.org/c-sharp-tuple-class/](https://www.geeksforgeeks.org/c-sharp-tuple-class/)

在 C# 中，Tuple 类用于提供创建 **[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)** 的静态方法，该类定义在*系统*命名空间下。这个类本身并不表示元组，但是它提供了用于创建元组类型实例的静态方法。或者换句话说，tuple 类提供了用于实例化 tuple 对象的辅助方法，而不必显式指定每个 Tuple 组件的类型。在元组中，你只能存储 1 到 8 个元素，如果你试图存储大于 8 的元素而没有嵌套元组，那么编译器会给出一个错误。

***一般使用元组:***

*   Represent multiple data as a single data set.
*   Create, manipulate and access data sets.
*   Returns multiple values from a method without using the out parameter.
*   Pass multiple values to a method with a single parameter.

**注意:**您也可以借助元组类提供的构造函数来创建元组，但是在构造函数中，您必须指定元组中存在的元素的类型，如下例所示:

**例:**

```cs
// C# program to create tuple 
// using tuple constructor.
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with seven elements
        // Using Tuple<T1, T2, T3, T4, T5, T6, 
        // T7>(T1, T2, T3, T4, T5, T6, T7) constructor
        Tuple<int, int, int, int, int, int, int> My_Tuple = new Tuple<int, 
               int, int, int, int, int, int>(22, 334, 54, 65, 76, 87, 98);

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

**输出:**

```cs
Element 1: 22
Element 2: 334
Element 3: 54
Element 4: 65
Element 5: 76
Element 6: 87
Element 7: 98

```