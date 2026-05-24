# 如何在 C# 中获取 ValueTuple 的第七个元素？

> 原文:[https://www . geeksforgeeks . org/如何获取 c-sharp 中的第七个值元素 tuple/](https://www.geeksforgeeks.org/how-to-get-seventh-element-of-the-valuetuple-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item7 属性**用于获取给定值元组的第七个未命名元素。它适用于每个值元组，如 7 值元组和 8 值元组。

**语法:**

```cs
public T7 Item7;
```

这里，T7 是 ValueTuple <>结构的字段值。该值元组<>可以是 7 值元组，也可以是 8 值元组。

**示例 1:** 在下面的代码中，可以看到我们正在访问每个值元组的第七个元素。

```cs
// C# program to illustrate how to get
// the seventh element of value tuple
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        Console.WriteLine("C# Topics:");

        // Creating a value tuple with seven elements
        var ValTpl7 = ValueTuple.Create("Inheritance ", "Constructors", 
                        "Encapsulation", "Abstraction", "Static Class",
                                    "Partial Classes", "this keyword");

        // Accessing the seventh element of 
        // 7-ValueTuple using Item property
        Console.WriteLine(ValTpl7.Item7);

        // Creating a value tuple with eight elements
        var ValTpl8 = ValueTuple.Create("Methods", "Method Hiding",
                        "Optional Parameters", "Anonymous Method",
                "Partial Methods", "Local Function", "Delegates",
                                                    "Destructors");

        // Accessing the seventh element of 
        // 8-ValueTuple using Item property
        Console.WriteLine(ValTpl8.Item7);
    }
}
```

**Output:**

```cs
C# Topics:
this keyword
Delegates

```

**例 2:**

```cs
// C# program to get the hash code of
// seventh element in a value tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 7-ValueTuple
        var My_Value_Tuple = (1004, "Rohit", "Computer Science", 
                                   24, "C#", 2017, "3-7-1993");

        // Accessing seventh element
        // of the value tuple
        Console.WriteLine("Birth Date: {0}",
                      My_Value_Tuple.Item7);

        // Getting the hashcode of 
        // the seventh element
        Console.WriteLine("Hash Code: {0}",
            My_Value_Tuple.Item7.GetHashCode());
    }
}
```

**Output:**

```cs
Birth Date: 3-7-1993
Hash Code: -1761317527

```