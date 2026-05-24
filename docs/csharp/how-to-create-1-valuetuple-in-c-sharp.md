# 如何在 C# 中创建 1 值元组？

> 原文:[https://www . geesforgeks . org/how-create-1-value tuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-1-valuetuple-in-c-sharp/)

在 C# 中，单值元组或 1 值元组是只包含一个组件的值类型元组。您可以使用两种不同的方法创建单值元组:

1.  **使用值元组< T1 > (T1)构造器**
2.  **使用创建< T1 > (T1)方法**

#### 使用值元组 <t1>(T1)构造函数</t1>

您可以使用 ValueTuple <t1>(T1)构造函数创建单例值 tuple。此构造函数初始化 ValueTuple <t1>结构的新实例。但是当您使用这个构造函数创建一个值元组时，您必须指定存储在值元组中的元素的类型。</t1></t1>

**语法:**

```cs
public ValueTuple (T1 item1);
```

这里， *item1* 是值元组的唯一组成部分。

**示例:**

```cs
// C# program to create singleton ValueTuple
// using the value tuple constructor
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with one element
        // Using ValueTuple<T1>(T1) constructor
        ValueTuple<string> MyTpl = new ValueTuple<string>("GeeksforGeeks");

        Console.WriteLine("Component is: " + MyTpl.Item1);
    }
}
```

**Output:**

```cs
Component is: GeeksforGeeks

```

#### 使用创建 <t1>(T1)方法</t1>

也可以借助 Create <t1>(T1)方法创建单值元组。当您使用此方法时，就不需要指定存储在值元组中的元素的类型。</t1>

**语法:**

```cs
public static ValueTuple<T1> Create<T1> (T1 item1);
```

这里， *item1* 是值元组组件的值， *T1* 是存储在值元组中的元素的类型。

**返回类型:**这个方法返回一个包含一个元素的值元组。

**示例:**

```cs
// C# program to create a singleton value 
// tuple using Create<T1>(T1) method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with one element
        // Using Create<T1>(T1) method
        var MyTple = ValueTuple.Create("Geeks123");

        Console.WriteLine("Component: " + MyTple.Item1);
    }
}
```

**Output:**

```cs
Component: Geeks123

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple-1。-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-1.-ctor?view=netframework-4.8)
*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple . create？view = net framework-4.8 # System _ ValueTuple _ Create _ _ 1 _ _ _ 0 _](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.create?view=netframework-4.8# System_ValueTuple_Create__1___0_)