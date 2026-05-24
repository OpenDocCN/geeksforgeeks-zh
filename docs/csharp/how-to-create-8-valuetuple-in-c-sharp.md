# 如何在 C# 中创建 8 值元组？

> 原文:[https://www . geesforgeks . org/how-create-8-value tuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-8-valuetuple-in-c-sharp/)

在 C# 中，8 值元组是包含 8 个元素的值类型元组，也称为**八元组**。您可以使用两种不同的方法创建 8 值元组:

1.  **使用 ValueTuple < T1、T2、T3、T4、T5、T6、T7、TRest < (T1、T2、T3、T4、T5、T6、T7、TRest)构造器**
2.  **使用创建< T1、T2、T3、T4、T5、T6、T7、T8 < (T1、T2、T3、T4、T5、T6、T7、T8)方法**

#### 使用 ValueTuple

您可以使用 ValueTuple

**语法:**

> 公共值元组(T1 项 1、T2 项 2、T3 项 3、T4 项 4、T5 项 5、T6 项 6、T7 项 7、TRest rest)；

**参数:**

*   **item1:** 是第一个值元组组件的值。
*   **item2:** 是第二个值元组组件的值。
*   **item3:** 是第三个值元组组件的值。
*   **item4:** 是第四个值元组组件的值。
*   **item5:** 是第五值元组分量的值。
*   **item6:** 是第六值元组分量的值。
*   **item7:** 是第七个值元组组件的值。
*   **rest:** 它是任何值元组类型的实例，包含值元组剩余元素的值。

**异常:**如果*休息*不是泛型值元组类型，这将给出*参数异常*。

**示例:**

```cs
// C# program to create a 8-ValueTuple
// using ValueTuple constructor
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with eight elements
        // Using ValueTuple<T1, T2, T3, T4, T5, T6,
        // T7, TRest>(T1, T2, T3, T4, T5, T6, T7, 
        // TRest rest) constructor
        ValueTuple<string, string, string, string, string, string,
          string, ValueTuple<string>> MyTpl = new ValueTuple<string,
                     string, string, string, string, string, string, 
                     ValueTuple<string>>("Rohan", "Sumit", "Soniya", 
                               "Shivam", "Raksha", "Purvi", "Mohan",
                                   new ValueTuple<string>("Nayan"));

        Console.WriteLine("Student 1: " + MyTpl.Item1);
        Console.WriteLine("Student 2: " + MyTpl.Item2);
        Console.WriteLine("Student 3: " + MyTpl.Item3);
        Console.WriteLine("Student 4: " + MyTpl.Item4);
        Console.WriteLine("Student 5: " + MyTpl.Item5);
        Console.WriteLine("Student 6: " + MyTpl.Item6);
        Console.WriteLine("Student 7: " + MyTpl.Item7);
        Console.WriteLine("Student 8: " + MyTpl.Rest);
    }
}
```

**Output:**

```cs
Student 1: Rohan
Student 2: Sumit
Student 3: Soniya
Student 4: Shivam
Student 5: Raksha
Student 6: Purvi
Student 7: Mohan
Student 8: (Nayan)

```

#### 使用创建< T1、T2、T3、T4、T5、T6、T7、T8

您还可以借助 Create

**语法:**

> 公共静态值元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" valuetuple="">>创建< T1, T2, T3, T4, T5, T6, T7, T8> (T1 项 1、T2 项 2、T3 项 3、T4 项 4、T5 项 5、T6 项 6、T7 项 7、T8 项 8)；</t1>

**类型参数:**

*   **T1:** 它是值元组的第一个组件的类型。
*   **T2:** 它是值元组的第二个组成部分的类型。
*   **T3:** 是值元组的第三个分量的类型。
*   **T4:** 它是值元组的第四个组成部分的类型。
*   **T5:** 它是值元组的第五个组成部分的类型。
*   **T6:** 它是值元组的第六个组成部分的类型。
*   **T7:** 它是值元组的第七个组成部分的类型。
*   **T8:** 它是值元组的第八个组成部分的类型。

**参数:**

*   **item1:** 它是值元组的第一个分量的值。
*   **item2:** 它是值元组的第二个分量的值。
*   **item3:** 它是值元组的第三个分量的值。
*   **item4:** 它是值元组的第四个分量的值。
*   **item5:** 它是值元组的第五个分量的值。
*   **item6:** 它是值元组的第六个分量的值。
*   **item7:** 它是值元组的第七个分量的值。
*   **item8:** 它是值元组的第八个分量的值。

**返回:**这个方法返回一个包含八个元素的值元组。

**示例:**

```cs
// C# program to create a 8-ValueTuple
// using Create Method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with the 
        // eight elements using Create method
        var MyTple = ValueTuple.Create(45.67, 67.78, 56.8, 567.5,
                                       23.4, 56.7, 12.34, 35.56);

        // Display the components of the value tuple
        Console.WriteLine("Component 1: " + MyTple.Item1);
        Console.WriteLine("Component 2: " + MyTple.Item2);
        Console.WriteLine("Component 3: " + MyTple.Item3);
        Console.WriteLine("Component 4: " + MyTple.Item4);
        Console.WriteLine("Component 5: " + MyTple.Item5);
        Console.WriteLine("Component 6: " + MyTple.Item6);
        Console.WriteLine("Component 7: " + MyTple.Item7);
        Console.WriteLine("Component 8: " + MyTple.Item7);
    }
}
```

**Output:**

```cs
Component 1: 45.67
Component 2: 67.78
Component 3: 56.8
Component 4: 567.5
Component 5: 23.4
Component 6: 56.7
Component 7: 12.34
Component 8: 12.34

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple-8。-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-8.-ctor?view=netframework-4.8)
*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple . create？view = net framework-4.8 # System _ ValueTuple _ Create _ _ 8 _ _ 0 _ _ 1 _ _ 2 _ _ 3 _ _ 4 _ _ 5 _ _ 6 _ _ 7 _](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.create?view=netframework-4.8# System_ValueTuple_Create__8___0___1___2___3___4___5___6___7_)