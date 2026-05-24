# c# 中的 ValueTuple 结构

> 原文:[https://www.geeksforgeeks.org/valuetuple-struct-in-c-sharp/](https://www.geeksforgeeks.org/valuetuple-struct-in-c-sharp/)

在 C# 中，ValueTuple 结构提供了用于创建 [**值元组**](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 的静态方法。它是在*系统*命名空间下定义的。在*中介绍。NET Framework 4.7* 提供 C# 中的运行时实现元组。ValueTuple 结构用于表示不包含任何元素的元组。通常，它提供用于创建或比较值元组的静态方法。借助 ValueTuple 结构的 Create 方法，您可以创建一个保存从 0 到 8 的元素的值 Tuple。它在以下方面不同于元组类:

*   它属于值类型，而不是引用类型。
*   它是可变的，而不是只读的。
*   在 ValueTuple 中，*项 1* 、*项 2* 、*项 3* 等。数据成员是字段而不是属性。

该结构实现了*可比较*、*可比较*、*可比较*、*可比较<值元组>T7、*可比较<值元组>T9】和*值元组*接口。**

#### 方法

| 方法 | 描述 |
| **比较(值元组)** | 将当前值元组实例与指定的值元组实例进行比较。 |
| **创建()** | 创建一个包含零个组件的新值元组。 |
| **创建< T1、T2、T3、T4、T5、T6、T7、T8 > (T1、T2、T3、T4、T5、T6、T7、T8)** | 创建一个包含 8 个组件(一个八元组)的新值元组。 |
| **创建< T1、T2、T3、T4、T5、T6、T7 > (T1、T2、T3、T4、T5、T6、T7)** | 创建一个包含 7 个组件(一个七元组)的新值元组。 |
| **创建< T1、T2、T3、T4、T5、T6 > (T1、T2、T3、T4、T5、T6)** | 创建一个包含 6 个组件(一个六元组)的新值元组。 |
| **创建< T1、T2、T3、T4、T5 > (T1、T2、T3、T4、T5)** | 创建一个包含 5 个组件的新值元组(五元组)。 |
| **创建< T1、T2、T3、T4 > (T1、T2、T3、T4)** | 创建一个包含 4 个组件(一个四元组)的新值元组。 |
| **创建< T1、T2、T3 > (T1、T2、T3)** | 创建一个包含 3 个组件(一个三元组)的新值元组。 |
| **创建< T1，T2 > (T1，T2)** | 创建包含 2 个组件(一对)的新值元组。 |
| **创建< T1 > (T1)** | 用 1 个组件(单例)创建一个新的值元组。 |
| **等于(值元组)** | 确定两个 ValueTuple 实例是否相等。此方法始终返回 true。 |
| **等于(对象)** | 返回一个值，该值指示当前 ValueTuple 实例是否等于指定的对象。 |
| **GetHashCode（）** | 返回当前 ValueTuple 实例的哈希代码。 |
| **ToString()** | 返回此 ValueTuple 实例的字符串表示形式。 |

**示例:**

```cs
// C# program to illustrate the 
// methods of ValueTuple struct
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with 
        // zero element using Create method
        var MyTple1 = ValueTuple.Create();

        // Using GetHashCode method
        Console.WriteLine("HashCode of a value tuple with "+
                 "zero elements: " + MyTple1.GetHashCode());

        // Creating a value tuple 
        var MyTple2 = ValueTuple.Create(56, 3);
        var MyTple3 = ValueTuple.Create(56, 45);

        // Using CompareTo method
        int res1 = MyTple2.CompareTo(MyTple3);

        // Display result
        Console.WriteLine("CompareTo Method Result: " + res1);
    }
}
```

**输出:**

```cs
HashCode of a value tuple with zero elements: 0
CompareTo Method Result: -1

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple?view=netframework-4.8)