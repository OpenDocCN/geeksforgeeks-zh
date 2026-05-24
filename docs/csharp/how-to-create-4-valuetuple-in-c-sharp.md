# 如何在 C# 中创建 4 值元组？

> 原文:[https://www . geesforgeks . org/how-create-4-value tuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-4-valuetuple-in-c-sharp/)

在 C# 中，四元组或四值元组是一个包含四个元素的值类型元组。您可以使用两种不同的方法创建四元组:

1.  **使用 ValueTuple < T1、T2、T3、T4 > (T1、T2、T3、T4)建造师**
2.  **使用创建< T1、T2、T3、T4 > (T1、T2、T3、T4)方法**

#### 使用 ValueTuple <t1 t2="" t3="" t4="">(T1，T2，T3，T4)构造器</t1>

可以使用 ValueTuple <t1 t2="" t3="" t4="">(T1，T2，T3，T4)构造函数创建一个四元组。它初始化了 ValueTuple <t1 t2="" t3="" t4="">结构的一个新实例。但是当您使用这个构造函数创建一个值元组时，您必须指定存储在值元组中的元素的类型。</t1></t1>

**语法:**

```cs
public ValueTuple (T1 item1, T2 item2, T3 item3, T4 item4);
```

**参数:**

*   **item1:** 是第一个值元组组件的值。
*   **item2:** 是第二个值元组组件的值。
*   **item3:** 是第三个值元组组件的值。
*   **item4:** 是第四个值元组组件的值。

**示例:**

```cs
// C# program to create a quadruple
// value tuple using value tuple constructor
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with four elements
        // Using ValueTuple<T1, T2, T3, T4>(T1, T2, T3, T4) constructor
        ValueTuple<string, string, string, string> MyTpl = new ValueTuple<string,
                             string, string, string>("Dog", "Cat", "Cow", "Pig");

        Console.WriteLine("Component 1: " + MyTpl.Item1);
        Console.WriteLine("Component 2: " + MyTpl.Item2);
        Console.WriteLine("Component 3: " + MyTpl.Item3);
        Console.WriteLine("Component 4: " + MyTpl.Item4);
    }
}
```

**Output:**

```cs
Component 1: Dog
Component 2: Cat
Component 3: Cow
Component 4: Pig

```

#### 使用创建 <t1 t2="" t3="" t4="">(T1、T2、T3、T4)方法</t1>

您也可以借助 Create <t1 t2="" t3="" t4="">(T1，T2，T3，T4)方法创建一个四元组或一个包含 4 个元素的元组。当您使用此方法时，就不需要指定存储在值元组中的元素的类型。</t1>

**语法:**

> 公共静态值元组<t1 t2="" t3="" t4="">创建 <t1 t2="" t3="" t4="">(T1 项 1、T2 项 2、T3 项 3、T4 项 4)；</t1></t1>

**类型参数:**

*   **T1:** 它是值元组的第一个组件的类型。
*   **T2:** 它是值元组的第二个组成部分的类型。
*   **T3:** 是值元组的第三个分量的类型。
*   **T4:** 它是值元组的第四个组成部分的类型。

**参数:**

*   **item1:** 它是值元组的第一个分量的值。
*   **item2:** 它是值元组的第二个分量的值。
*   **item3:** 它是值元组的第三个分量的值。
*   **item4:** 它是值元组的第四个分量的值。

**返回类型:**这个方法返回一个包含四个元素的值元组。

**示例:**

```cs
// C# program to create a quadruple value tuple
// using Create<T1, T2, T3, T4>(T1, T2, T3, 
// T4) method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with four elements
        // Using Create<T1, T2, T3, T4>(T1, T2, T3, T4)
        // method
        var MyTple = ValueTuple.Create(12, 34, 56, 45);

        Console.WriteLine("Component 1: " + MyTple.Item1);
        Console.WriteLine("Component 2: " + MyTple.Item2);
        Console.WriteLine("Component 3: " + MyTple.Item3);
        Console.WriteLine("Component 4: " + MyTple.Item4);
    }
}
```

**Output:**

```cs
Component 1: 12
Component 2: 34
Component 3: 56
Component 4: 45

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple-4。-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-4.-ctor?view=netframework-4.8)
*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple . create？view = net framework-4.8 # System _ ValueTuple _ Create _ _ 4 _ _ 0 _ _ 1 _ _ 2 _ _ 3 _](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.create?view=netframework-4.8# System_ValueTuple_Create__4___0___1___2___3_)