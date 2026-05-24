# c# 中装箱和拆箱的区别

> 原文:[https://www . geesforgeks . org/c-sharp 中装箱和拆箱的区别/](https://www.geeksforgeeks.org/difference-between-boxing-and-unboxing-in-c-sharp/)

**[打拳拆箱](https://www.geeksforgeeks.org/c-sharp-boxing-unboxing/)** 是 C# 中的一个重要概念。C# Type 系统包含三种数据类型:*值类型(int、char 等)*、*引用类型(object)* 和*指针类型*。基本上，它将值类型转换为引用类型，反之亦然。装箱和取消装箱实现了类型系统的统一视图，其中任何类型的值都可以被视为对象。

| 拳击 | 取消订阅 |
| 它将值类型转换为对象类型。 | 它将对象类型转换为值类型。 |
| 拳击是一个隐含的转换过程。 | 取消装箱是显式的转换过程。 |
| 这里，存储在堆栈上的值被复制到存储在堆内存中的对象上。 | 这里，存储在堆内存中的对象被复制到存储在堆栈中的值。 |
| **Example:**

```cs
// C# program to illustrate Boxing
using System;

public class GFG {
    static public void Main()
    {
        int val = 2019;

        // Boxing
        object o = val;

        // Change the value of val
        val = 2000;

        Console.WriteLine("Value type of val is {0}", val);
        Console.WriteLine("Object type of val is {0}", o);
    }
}
```

**输出:**

```cs
Value type of val is 2000
Object type of val is 2019

```

 | **Example:**

```cs
// C# program to illustrate Unboxing
using System;

public class GFG {
    static public void Main()
    {
        int val = 2019;

        // Boxing
        object o = val;

        // Unboxing
        int x = (int)o;

        Console.WriteLine("Value of o is {0}", o);
        Console.WriteLine("Value of x is {0}", x);
    }
}
```

**输出:**

```cs
Value of o is 2019
Value of x is 2019

```

 |