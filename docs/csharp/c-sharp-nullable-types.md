# C# |可空类型

> 原文:[https://www.geeksforgeeks.org/c-sharp-nullable-types/](https://www.geeksforgeeks.org/c-sharp-nullable-types/)

在 C# 中，编译器不允许您将空值赋给变量。因此， **C# 2.0** 提供了一个特殊的特性，为一个称为可空类型的变量分配一个空值。可空类型允许您将空值赋给变量。C# 2.0 中引入的可空类型只能用于[值类型](https://www.geeksforgeeks.org/c-data-types-2/)，不能用于[引用类型](https://www.geeksforgeeks.org/c-data-types-2/)。

引用类型的可空类型稍后将在 2019 年的 C# 8.0 中介绍，这样我们就可以明确定义引用类型是否可以包含空值。这帮助我们在不使用条件的情况下解决了 NullReferenceException 的问题。在本文中，讨论围绕值类型的可空类型展开。

可空类型是*系统的一个实例。可空< T >结构*。这里的 T 是一个包含不可空值类型的类型，如整数类型、浮点类型、布尔类型等。例如，在整数类型的可空中，可以存储从-2147483648 到 2147483647 的值，或者空值。

**语法:**

```cs
Nullable<data_type> variable_name = null;

```

或者也可以使用包含**的快捷方式？**数据类型的运算符。

```cs
datatype? variable_name = null;

```

**示例:**

```cs
// this will give compile time error
int j = null;           

// Valid declaration
Nullable<int> j = null;   

// Valid declaration
int? j = null;           

```

**如何访问可空类型变量的值？**
您不能直接访问可空类型的值。如果原始赋值不为空，则必须使用 **GetValueOrDefault()方法**来获取原始赋值。如果默认值为空，您将获得默认值。null 的默认值将为零。

**示例:**

## C#

```cs
// C# program to illustrate Nullable Types
using System;

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // defining Nullable type
        Nullable<int> n = null;

        // using the method
        // output will be 0 as default
        // value of null is 0
        Console.WriteLine(n.GetValueOrDefault());

        // defining Nullable type
        int? n1 = null;

        // using the method
        // output will be 0 as default
        // value of null is 0
        Console.WriteLine(n1.GetValueOrDefault());

        // using Nullable type syntax
        // to define non-nullable
        int? n2 = 47;

        // using the method
        Console.WriteLine(n2.GetValueOrDefault());

        // using Nullable type syntax
        // to define non-nullable
        Nullable<int> n3 = 457;

        // using the method
        Console.WriteLine(n3.GetValueOrDefault());

    }

}
```

**输出:**

```cs
0
0
47
457

```

#### 可空类型的特征

*   在可空类型的帮助下，您可以将空值赋给变量，而无需基于引用类型创建可空类型。
*   在可空类型中，还可以为可空类型赋值。如下例所示。

**示例:**

## C#

```cs
// C# program to illustrate the
// use of Nullable type
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // a is nullable type
        // and contains null value
        int ? a = null;

        // b is nullable type int
        // and behave as a normal int
        int ? b = 2345;

        // this will not print
        // anything on console
        Console.WriteLine(a);

        // gives 2345 as output
        Console.WriteLine(b);
    }
}
```

**输出:**

```cs
2345

```

*   可以使用**可空。哈希值**和**可空。数值**检查数值。如果对象被赋值，那么它将返回“真”，如果对象被赋值为空，那么它将返回“假”。如果对象没有被赋予任何值，那么它将给出编译时错误。

**示例:**

## C#

```cs
// C# program to illustrate the
// use of Nullable<L>.Hasvalue
using System;

class GFG {

    // Main Method
    static void Main()
    {

        // a is nullable type
        // and contains null value
        Nullable<int> a = null;

        // check the value of object
        Console.WriteLine(a.HasValue);

        // b is nullable type
        // and contains a value
        Nullable<int> b = 7;

        // check the value of object
        Console.WriteLine(b.HasValue);

    }
}
```

**输出:**

```cs
False
True

```

*   也可以使用==和！可空类型的运算符。
*   如果可空类型的值为空，也可以使用**getvalueorddefault(T)方法**获取赋值或提供的默认值。
*   也可以使用**空值合并运算符(？？)**为基础类型赋值源于可空类型的值。

**示例:**

## C#

```cs
// C# program to illustrate the
// use of  null-coalescing operator(??)
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // a is nullable type
        // and contains null value
        int ? a = null;

        // it means if a is null
        // then assign 3 to b
        int b = a ?? 3;

        // It will print 3
        Console.WriteLine(b);
    }
}
```

**输出:**

```cs
3

```

*   可空类型不支持嵌套的可空类型。
*   可空类型不支持 var 类型。如果您将 Nullable 与 var 一起使用，那么编译器会给您一个编译时错误。

**可空类型的优势:**

*   可空类型的主要用途是在数据库应用中。假设一个表中的一列需要空值，那么可以使用可空类型输入空值。
*   可空类型对于表示未定义的值也很有用。
*   也可以使用可空类型代替引用类型来存储空值。