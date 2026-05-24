# LINQ |生成运算符|空、范围和重复

> 原文:[https://www . geesforgeks . org/linq-generation-operator-empty-range-and-repeat/](https://www.geeksforgeeks.org/linq-generation-operator-empty-range-and-repeat/)

生成运算符用于创建新的值序列。标准查询运算符支持 **4** 种不同类型的生成运算符:

1.  **[【default ifying】](https://www.geeksforgeeks.org/linq-generation-operator-defaultifempty/)**
2.  **清空**
3.  **范围**
4.  **重复**

#### 空运算符

空运算符用于返回空集合。或者换句话说，我们可以说它返回了一个包含指定类型参数的空 IEnumerable <t>。</t>

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它只出现在可枚举类中。

**示例:**

```cs
// C# program to illustrate the
// concept of Empty operator
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Query which return empty collection
        // Using Empty method
        var res = Enumerable.Empty<string>();

        // Display the total number of elements
        // present in the given collection
        Console.WriteLine("How many elements present"+
              "in the collection?: {0}", res.Count());

        // Display the type in the given collection
        Console.WriteLine("Type is: {0}", res.GetType().Name);
    }
}
```

**Output:**

```cs
How many elements presentin the collection?: 0
Type is: String[]

```

#### 距离操作手

Range 运算符用于生成包含一系列数字的集合。或者换句话说，它是用来返回一个带有给定范围内整数序列的 IEnumerable <t>类型的集合。</t>

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它只出现在可枚举类中。
*   如果计数值小于零或 *start+count-1* 大于最大值，它将抛出 ArgumentOutOfRangeException。
*   它通过使用延迟执行来实现。

**示例:**

```cs
// C# program to illustrate the
// concept of Range operator
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Query which provides 10 elements
        // starting from 100
        // Using Range method
        var res = Enumerable.Range(100, 10);

        // Display elements
        Console.WriteLine("Elements are:");
        foreach(var val in res)
        {
            Console.WriteLine(val);
        }

        // Display the total number of elements
        // present in the given collection
        Console.WriteLine("How many elements present"+
             " in the collection?: {0}", res.Count());
    }
}
```

**Output:**

```cs
Elements are:
100
101
102
103
104
105
106
107
108
109
How many elements present in the collection?: 10

```

#### 重复操作符

repeat 运算符用于创建保存一个重复值的集合。或者换句话说，我们可以说它是用来创建带有重复项目数的 IEnumerable <t>类型。</t>

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它只出现在可枚举类中。
*   如果计数值小于零，它将引发 ArgumentOutOfRangeException。
*   它通过使用延迟执行来实现。

**示例:**

```cs
// C# program to illustrate the 
// concept of Repeat operator
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Query which repeats a string
        // 10 times
        // Using Range method
        var res = Enumerable.Repeat("Welcome to GeeksforGeeks", 10);

        // Display repeated collection
        foreach(var val in res)
        {
            Console.WriteLine(val);
        }

        // Display the total times 
        // the element repeat
        Console.WriteLine("How many times the string"+
                  " repeat?: {0} times", res.Count());
    }
}
```

**Output:**

```cs
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
How many times the string repeat?: 10 times

```