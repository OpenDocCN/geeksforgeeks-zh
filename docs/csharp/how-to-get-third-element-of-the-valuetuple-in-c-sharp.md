# 如何在 C# 中获取 ValueTuple 的第三个元素？

> 原文:[https://www . geeksforgeeks . org/如何获取 c-sharp 中的第三个值元素 tuple/](https://www.geeksforgeeks.org/how-to-get-third-element-of-the-valuetuple-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item3 属性**用于获取给定值元组的第三个未命名元素。它适用于每个值元组，如 3 值元组、4 值元组等。

**语法:**

```cs
public T3 Item3;
```

这里，T3 是 ValueTuple <>结构的字段值。该值元组<>可以是 3 值元组、4 值元组、5 值元组、6 值元组、7 值元组或 8 值元组。

**示例:**在下面的代码中，可以看到我们正在访问每个值元组的第三个元素。

```cs
// C# program to illustrate how to get
// the third element of value tuple
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        Console.WriteLine("C# Topics:");

        // Creating a value tuple
        // with three elements
        var ValTpl3 = ValueTuple.Create("ArrayList",
                                     "List", "Queue");

        // Accessing the third element of 
        // 3-ValueTuple using Item property
        Console.WriteLine(ValTpl3.Item3);

        // Creating a value tuple 
        // with four elements
        var ValTpl4 = ValueTuple.Create("Stack", "Dictionary",
                                "LinkedList", "Interface");

        // Accessing the third element of 
        // 4-ValueTuple using Item property
        Console.WriteLine(ValTpl4.Item3);

        // Creating a value tuple with five elements
        var ValTpl5 = ValueTuple.Create("Identifiers", "Data Types",
                    "Keywords", "Access Modifiers", "Operators");

        // Accessing the third element of 
        // 5-ValueTuple using Item property
        Console.WriteLine(ValTpl5.Item3);

        // Creating a value tuple with six elements
        var ValTpl6 = ValueTuple.Create("Nullable Types", "Class",
            "Structure", "Indexers", "Switch Statement", "Loops");

        // Accessing the third element of 
        // 6-ValueTuple using Item property
        Console.WriteLine(ValTpl6.Item3);

        // Creating a value tuple with seven elements
        var ValTpl7 = ValueTuple.Create("Inheritance ", "Constructors", 
                        "Encapsulation", "Abstraction", "Static Class",
                                    "Partial Classes", "this keyword");

        // Accessing the third element of 
        // 7-ValueTuple using Item property
        Console.WriteLine(ValTpl7.Item3);

        // Creating a value tuple with eight elements
        var ValTpl8 = ValueTuple.Create("Methods", "Method Hiding",
                        "Optional Parameters", "Anonymous Method",
                "Partial Methods", "Local Function", "Delegates",
                                                    "Destructors");

        // Accessing the third element of 
        // 8-ValueTuple using Item property
        Console.WriteLine(ValTpl8.Item3);
    }
}
```

**Output:**

```cs
C# Topics:
Queue
LinkedList
Keywords
Structure
Encapsulation
Optional Parameters

```