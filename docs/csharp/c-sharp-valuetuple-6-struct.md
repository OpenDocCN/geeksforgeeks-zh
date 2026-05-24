# c# | value tuple<t1>Struct</t1>T3】

> 原文:[https://www.geeksforgeeks.org/c-sharp-valuetuple-6-struct/](https://www.geeksforgeeks.org/c-sharp-valuetuple-6-struct/)

ValueTuple <t1>结构用于创建六元组或六值元组。它表示一个存储六个元素的值元组。它提供了[值元组](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/)的运行时实现。您可以使用 *ValueTuple < T1、T2、T3、T4、T5、T6 > (T1、T2、T3、T4、T5、T6)构造函数*或使用 *ValueTuple 创建 ValueTuple < T1、T2、T3、T4、T5、T6 >结构的实例。创建方法*或简单地使用*括号()*。您可以通过使用默认属性来检索值元组的未命名元素的值，或者可以借助命名元素的名称来直接访问它们。</t1>

**要点:**

*   它实现了*可比较的*、*可比较的*、*可比较的*、*可比较的<值元组< T1、T2、T3、T4、T5、T6 > >* 、*可比较的<值元组< T1、T2、T3、T4、T5、T6 > >和 *ITuple* 接口。*
*   它是在系统命名空间下定义的。
*   它还可以存储重复的元素。
*   字段是可变的。因此，您可以更改 ValueTuple <t1>Struct 的值。</t1>
*   在这里，像*项 1* 、*项 2* 、*项 3* 、*项 4* 、*项 5* 、*项 6* 这样的成员是字段，不是属性。
*   它的值类型不是引用类型。
*   它将多个数据表示成一个数据集。
*   它允许在单个参数的帮助下向一个方法传递多个值。

#### 构造器

| 构造器 | 描述 |
| **值元组< T1、T2、T3、T4、T5、T6 > (T1、T2、T3、T4、T5、T6)** | 初始化一个新的 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例。</t1> |

#### 田

| 田 | 描述 |
| **第 1 项** | 获取当前 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例的第一个元素的值。</t1> | **第 2 项** | 获取当前 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例的第二个元素的值。</t1> | **第 3 项** | 获取当前 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例的第三个元素的值。</t1> | **第 4 项** | 获取当前 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例的第四个元素的值。</t1> | **第 5 项** | 获取当前 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例的第五个元素的值。</t1> | **第 6 项** | 获取当前 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例的第六个元素的值。</t1> |

**示例:**

```cs
// C# program to illustrate how to
// access the element of ValueTuple<T1, 
// T2, T3, T4, T5, T6>
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating a value tuple
        // Using Create method
        var Mylibrary = ValueTuple.Create(3456, "The Guide", "R. K. Narayan",
                                     1958, "Philosophical novel", "English");

        // Display the element of the given value tuple
        Console.WriteLine("Book Details: ");
        Console.WriteLine("Book Id: {0}", Mylibrary.Item1);
        Console.WriteLine("Book Name: {0}", Mylibrary.Item2);
        Console.WriteLine("Author Name: {0}", Mylibrary.Item3);
        Console.WriteLine("Publication date: {0}", Mylibrary.Item4);
        Console.WriteLine("Gener: {0}", Mylibrary.Item5);
        Console.WriteLine("Language: {0}", Mylibrary.Item6);
    }
}
```

**Output:**

```cs
Book Details: 
Book Id: 3456
Book Name: The Guide
Author Name: R. K. Narayan
Publication date: 1958
Gener: Philosophical novel
Language: English

```

#### 方法

| 方法 | 描述 |
| **比较(值元组)** | 将当前值元组<t1 t2="" t3="" t4="" t5="" t6="">实例与指定的值元组<t1 t2="" t3="" t4="" t5="" t6="">实例进行比较。</t1></t1> |
| **等于(对象)** | 返回一个值，该值指示当前值元组<t1 t2="" t3="" t4="" t5="" t6="">实例是否等于指定的对象。</t1> |
| **等于(值元组)** | 返回一个值，该值指示当前值元组<t1 t2="" t3="" t4="" t5="" t6="">实例是否等于指定的值元组<t1 t2="" t3="" t4="" t5="" t6="">实例。</t1></t1> |
| **GetHashCode（）** | 计算当前值元组<t1 t2="" t3="" t4="" t5="" t6="">实例的哈希代码。</t1> |
| **ToString()** | 返回一个字符串，该字符串表示该 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="">实例的值。</t1>  |

**示例:**

```cs
// C# program to check the given value 
// tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 6-ValueTuple
        // Using Create method
        var T1 = ValueTuple.Create(3, 2, 4, 5, 6, 7);
        var T2 = ValueTuple.Create(3, 2, 4, 5, 6, 7);

        // Check if both the value 
        // tuples are equal or not
        if (T1.Equals(T2)) 
        {
            Console.WriteLine("Code is correct...!!");
        }

        else 
        {
            Console.WriteLine("Incorrect Code...!!");
        }
    }
}
```

**Output:**

```cs
Code is correct...!!

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple-6？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-6?view=netframework-4.8)