# 如何在 C# 中创建 7 值元组？

> 原文:[https://www . geesforgeks . org/如何创建-7-valuetuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-7-valuetuple-in-c-sharp/)

在 C# 中，7 值元组是包含 7 个元素的值类型元组，也称为*七元组*。您可以使用两种不同的方法创建一个 7 值元组:

1.  **使用 ValueTuple < T1、T2、T3、T4、T5、T6、T7 > (T1、T2、T3、T4、T5、T6、T7)构造器**
2.  **使用创建< T1、T2、T3、T4、T5、T6、T7 > (T1、T2、T3、T4、T5、T6、T7)方法**

#### 使用 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="" t7="">(T1、T2、T3、T4、T5、T6、T7)构造器</t1>

您可以使用 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="" t7="">(T1、T2、T3、T4、T5、T6、T7)构造函数创建一个 7 值 Tuple。它初始化了 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="" t7="">结构的一个新实例。但是当您使用这个构造函数创建一个值元组时，您必须指定存储在值元组中的元素的类型。</t1></t1>

**语法:**

> 公共值元组(T1 项目 1、T2 项目 2、T3 项目 3、T4 项目 4、T5 项目 5、T6 项目 6、T7 项目 7)；

**参数:**

*   **item1:** 是第一个值元组组件的值。
*   **item2:** 是第二个值元组组件的值。
*   **item3:** 是第三个值元组组件的值。
*   **item4:** 是第四个值元组组件的值。
*   **item5:** 是第五值元组分量的值。
*   **item6:** 是第六值元组分量的值。
*   **item7:** 是第七个值元组组件的值。

**示例:**

```cs
// C# program to create a 7-ValueTuple
// using value tuple constructor
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with seven elements
        // Using ValueTuple<T1, T2, T3, T4, T5, T6,
        // T7>(T1, T2, T3, T4, T5, T6, T7) constructor
        ValueTuple<string, string, string, string, string, string,
            string> MyTpl = new ValueTuple<string, string, string, 
              string, string, string, string>("Dog", "Cat", "Cow",
                                    "Pig", "Hen", "Bird", "Fish");

        Console.WriteLine("Component 1: " + MyTpl.Item1);
        Console.WriteLine("Component 2: " + MyTpl.Item2);
        Console.WriteLine("Component 3: " + MyTpl.Item3);
        Console.WriteLine("Component 4: " + MyTpl.Item4);
        Console.WriteLine("Component 5: " + MyTpl.Item5);
        Console.WriteLine("Component 6: " + MyTpl.Item6);
        Console.WriteLine("Component 7: " + MyTpl.Item7);
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
Component 6: Bird
Component 7: Fish

```

#### 使用创建 <t1 t2="" t3="" t4="" t5="" t6="" t7="">(T1、T2、T3、T4、T5、T6、T7)方法</t1>

您也可以借助 Create <t1 t2="" t3="" t4="" t5="" t6="" t7="">(T1、T2、T3、T4、T5、T6、T7)方法创建一个 7 值元组或一个包含 7 个元素的值元组。当您使用此方法时，就不需要指定存储在值元组中的元素的类型。</t1>

**语法:**

> 公共静态值元组<t1 t2="" t3="" t4="" t5="" t6="" t7="">创建 <t1 t2="" t3="" t4="" t5="" t6="" t7="">(T1 项 1、T2 项 2、T3 项 3、T4 项 4、T5 项 5、T6 项 6、T7 项 7)；</t1></t1>

**类型参数:**

*   **T1:** 它是值元组的第一个组件的类型。
*   **T2:** 它是值元组的第二个组成部分的类型。
*   **T3:** 是值元组的第三个分量的类型。
*   **T4:** 它是值元组的第四个组成部分的类型。
*   **T5:** 它是值元组的第五个组成部分的类型。
*   **T6:** 它是值元组的第六个组成部分的类型。
*   **T7:** 它是值元组的第七个组成部分的类型。

**参数:**

*   **item1:** 它是值元组的第一个分量的值。
*   **item2:** 它是值元组的第二个分量的值。
*   **item3:** 它是值元组的第三个分量的值。
*   **item4:** 它是值元组的第四个分量的值。
*   **item5:** 它是值元组的第五个分量的值。
*   **item6:** 它是值元组的第六个分量的值。
*   **item7:** 它是值元组的第七个分量的值。

**返回:**这个方法返回一个包含七个元素的值元组。

**示例:**

```cs
// C# program to create a 7-ValueTuple
// using Create<T1, T2, T3, T4, T5, T6,
// T7>(T1, T2, T3, T4, T5, T6, T7) Method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with seven elements
        // Using Create<T1, T2, T3, T4, T5, T6, 
        // T7>(T1, T2, T3, T4, T5, T6, T7) method
        var MyTple = ValueTuple.Create(12, 34, 56, 45,
                                          67, 89, 78);

        Console.WriteLine("Component 1: " + MyTple.Item1);
        Console.WriteLine("Component 2: " + MyTple.Item2);
        Console.WriteLine("Component 3: " + MyTple.Item3);
        Console.WriteLine("Component 4: " + MyTple.Item4);
        Console.WriteLine("Component 5: " + MyTple.Item5);
        Console.WriteLine("Component 6: " + MyTple.Item6);
        Console.WriteLine("Component 7: " + MyTple.Item7);
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
Component 6: 89
Component 7: 78

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple-7。-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-7.-ctor?view=netframework-4.8)
*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple . create？view = net framework-4.8 # System _ ValueTuple _ Create _ _ 7 _ _ 0 _ _ 1 _ _ 2 _ _ 3 _ _ 4 _ _ 5 _ _ 6 _](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.create?view=netframework-4.8# System_ValueTuple_Create__7___0___1___2___3___4___5___6_)