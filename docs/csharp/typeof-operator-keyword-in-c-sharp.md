# c# 中运算符关键字的类型

> 原文:[https://www . geesforgeks . org/type of-operator-keyword-in-c-sharp/](https://www.geeksforgeeks.org/typeof-operator-keyword-in-c-sharp/)

的 ***类型是一个运算符关键字，用于在编译时获取类型。或者换句话说，这个运算符用于获取系统。类型的类型对象。该运算符将*类型*本身作为参数，并返回参数的标记类型。
**要点:***** 

*   运算符的*类型的操作数始终是参数的类型或类型的名称。它不包含变量。*
*   不允许霸王操作员的*类型。*
*   允许在打开的泛型类型上使用运算符的*类型。*
*   允许在有界或无界类型上使用运算符的*类型。*

**语法:**

```cs
System.Type type = typeof(int);
```

这里，*类型*是获得的类型。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// concept of typeof operator
using System;

class GFG {

    // Here store Type as a field
    static Type a = typeof(double);

    // Main method
    static void Main()
    {

        // Display the type of a
        Console.WriteLine(a);

        // Display the value type
        Console.WriteLine(typeof(int));

        // Display the class type
        Console.WriteLine(typeof(Array));

        // Display the value type
        Console.WriteLine(typeof(char));

        // Display the array reference type
        Console.WriteLine(typeof(int[]));
    }
}
```

**输出:**

```cs
System.Double
System.Int32
System.Array
System.Char
System.Int32[]
```

#### 运算符的*类型与 *GetType* 方法的区别*

<figure class="table">

| 操作员类型 | 获取类型方法 |
| 它将类型本身作为参数，并返回参数的标记类型。 | 它只在类型的实例上调用。 |
| 它用于获取编译时已知的类型。 | 它用于在运行时获取对象的类型。 |
| 它不能在实例上使用。 | 它可以在实例上使用。 |

</figure>

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// difference between typeof
// operator and GetType method
using System;

public class GFG {

    // Main method
    static public void Main()
    {
        string s = "Geeks";

        // using typeof operator
        Type a1 = typeof(string);

        // using GetType method
        Type a2 = s.GetType();

        // checking for equality
        Console.WriteLine(a1 == a2);

        // taking a type object
        object obj = "Hello";

        // using typeof operator
        Type b1 = typeof(object);

        // using GetType method
        Type b2 = obj.GetType();

        // checking for equality
        // it will return False as
        // GetType method is used
        // to obtain run-time type
        Console.WriteLine(b1 == b2);
    }
}
```

**输出:**

```cs
True
False
```

**说明:**这里，Type b1 = typeof(对象)；这将返回*系统。对象*但类型 b2 =对象。GetType()；将返回*系统。弦*。因为，在编译时只创建对象类型引用，但是在运行时字符串(“Hello”)实际上存储在其中。