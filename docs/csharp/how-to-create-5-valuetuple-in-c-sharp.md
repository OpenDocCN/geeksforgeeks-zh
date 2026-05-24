# 如何在 C# 中创建 5 值元组？

> 原文:[https://www . geesforgeks . org/如何创建-5-valuetuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-5-valuetuple-in-c-sharp/)

在 C# 中，5 值元组或五元组是包含五个元素的值类型元组。您可以使用两种不同的方法创建一个 5 值元组:

1.  **使用 ValueTuple < T1、T2、T3、T4、T5 > (T1、T2、T3、T4、T5)建造师**
2.  **使用创建< T1、T2、T3、T4、T5 > (T1、T2、T3、T4、T5)方法**

#### 使用 ValueTuple <t1 t2="" t3="" t4="" t5="">(T1、T2、T3、T4、T5)构造器</t1>

您可以使用 ValueTuple <t1 t2="" t3="" t4="" t5="">(T1、T2、T3、T4、T5)构造函数创建一个五元组。它初始化了 ValueTuple <t1 t2="" t3="" t4="" t5="">结构的一个新实例。但是当您使用这个构造函数创建一个值元组时，您必须指定存储在值元组中的元素的类型。</t1></t1>

**语法:**

```cs
public ValueTuple (T1 item1, T2 item2, T3 item3, T4 item4, T5 item5);
```

**参数:**

*   **item1:** 是第一个值元组组件的值。
*   **item2:** 是第二个值元组组件的值。
*   **item3:** 是第三个值元组组件的值。
*   **item4:** 是第四个值元组组件的值。
*   **item5:** 是第五值元组分量的值。

**示例:**

```cs
// C# program to create a quintuple
// value tuple using value tuple constructor
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with five elements
        // Using ValueTuple<T1, T2, T3, T4, T5>(T1, T2, T3, T4, T5) constructor
        ValueTuple<string, string, string, string, string> MyTpl = new ValueTuple<string, string,
                                      string, string, string>("Dog", "Cat", "Cow", "Pig", "Hen");

        Console.WriteLine("Component 1: " + MyTpl.Item1);
        Console.WriteLine("Component 2: " + MyTpl.Item2);
        Console.WriteLine("Component 3: " + MyTpl.Item3);
        Console.WriteLine("Component 4: " + MyTpl.Item4);
        Console.WriteLine("Component 5: " + MyTpl.Item5);
    }
}
```

**Output:**

```cs
Component 1: Dog
Component 2: Cat
Component 3: Cow
Component 4: Pig
Component 5: Hen

```

#### 使用创建 <t1 t2="" t3="" t4="" t5="">(T1、T2、T3、T4、T5)方法</t1>

您也可以借助 Create <t1 t2="" t3="" t4="" t5="">(T1，T2，T3，T4，T5)方法创建一个五元组值元组或一个包含 5 个元素的值元组。当您使用此方法时，就不需要指定存储在值元组中的元素的类型。</t1>

**语法:**

> 公共静态值元组<t1 t2="" t3="" t4="" t5="">创建 <t1 t2="" t3="" t4="" t5="">(T1 项 1、T2 项 2、T3 项 3、T4 项 4、T5 项 5)；</t1></t1>

**类型参数:**

*   **T1:** 它是值元组的第一个组件的类型。
*   **T2:** 它是值元组的第二个组成部分的类型。
*   **T3:** 是值元组的第三个分量的类型。
*   **T4:** 它是值元组的第四个组成部分的类型。
*   **T5:** 它是值元组的第五个组成部分的类型。

**参数:**

*   **item1:** 它是值元组的第一个分量的值。
*   **item2:** 它是值元组的第二个分量的值。
*   **item3:** 它是值元组的第三个分量的值。
*   **item4:** 它是值元组的第四个分量的值。
*   **item5:** 它是值元组的第五个分量的值。

**返回:**这个方法返回一个包含五个元素的值元组。

**示例:**

```cs
// C# program to create a quintuple value tuple
// using Create<T1, T2, T3, T4, T5>(T1, T2, T3,
// T4, T5) method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with five elements
        // Using Create<T1, T2, T3, T4, T5>(T1, T2, 
        // T3, T4, T5) method
        var MyTple = ValueTuple.Create(12, 34, 56, 45, 67);

        Console.WriteLine("Component 1: " + MyTple.Item1);
        Console.WriteLine("Component 2: " + MyTple.Item2);
        Console.WriteLine("Component 3: " + MyTple.Item3);
        Console.WriteLine("Component 4: " + MyTple.Item4);
        Console.WriteLine("Component 5: " + MyTple.Item5);
    }
}
```

**Output:**

```cs
Component 1: 12
Component 2: 34
Component 3: 56
Component 4: 45
Component 5: 67

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple-5。-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-5.-ctor?view=netframework-4.8)
*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple . create？view = net framework-4.8 # System _ ValueTuple _ Create _ _ 5 _ _ 0 _ _ 1 _ _ 2 _ _ 3 _ _ 4 _](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.create?view=netframework-4.8# System_ValueTuple_Create__5___0___1___2___3___4_)