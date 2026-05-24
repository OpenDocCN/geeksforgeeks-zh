# C# 中 typeof 运算符关键字

> 原文：[https://www.geeksforgeeks.org/typeof-operator-keyword-in-c-sharp/](https://www.geeksforgeeks.org/typeof-operator-keyword-in-c-sharp/)

`typeof` 是一个运算符关键字，用于在编译时获取类型。或者换句话说，这个运算符用于获取 `System.Type` 的类型对象。该运算符将类型本身作为参数，并返回参数的 `System.Type` 类型。

**要点：**

*   `typeof` 运算符的操作数始终是参数的类型或类型的名称。它不包含变量。
*   不允许对 `typeof` 使用一元运算符。
*   允许在打开的泛型类型上使用 `typeof` 运算符。
*   允许在有界或无界类型参数上使用 `typeof` 运算符。

**语法：**

```cs
System.Type type = typeof(int);
```

这里，`typeof` 是获得的类型。

**例：**

## 示例 1

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

**输出：**

```cs
System.Double
System.Int32
System.Array
System.Char
System.Int32[]
```

#### typeof 运算符与 GetType 方法的区别

| typeof 运算符 | GetType 方法 |
| :--- | :--- |
| 它将类型本身作为参数，并返回参数的 `System.Type` 类型。 | 它只在类型的实例上调用。 |
| 它用于获取编译时已知的类型。 | 它用于在运行时获取对象的类型。 |
| 它不能在实例上使用。 | 它可以在实例上使用。 |

**例：**

## 示例 2

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

**输出：**

```cs
True
False
```

**说明：** 这里，`Type b1 = typeof(object);` 这将返回 `System.Object` 但 `Type b2 = obj.GetType();` 将返回 `System.String`。因为，在编译时只创建 `object` 类型引用，但是在运行时字符串 (`"Hello"`) 实际上存储在其中。