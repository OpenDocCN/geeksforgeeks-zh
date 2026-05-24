# C# | Tuple <t1>类</t1>T3】

> 原文:[https://www.geeksforgeeks.org/c-sharp-tuple-1-class/](https://www.geeksforgeeks.org/c-sharp-tuple-1-class/)

元组<t1>类用于创建 1 元组或单元组，其中只包含一个元素。您可以通过调用 **[元组< T1 >构造函数](https://www.geeksforgeeks.org/how-to-create-1-tuple-or-singleton-tuple-in-c-sharp/# Using%20Tuple%3CT1%3E(T1)%20Constructor)** 或静态 **[元组来实例化元组<t1>对象。创建</t1>](https://www.geeksforgeeks.org/how-to-create-1-tuple-or-singleton-tuple-in-c-sharp/# Using%20the%20Create%20method)** 方法。您可以通过使用只读*项目 1* 实例属性来检索元组的单个元素的值。</t1>

**要点:**

*   它实现了*结构可比较*、*结构可比较*、*我可比较*接口。
*   它是在系统命名空间下定义的。
*   它将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用 out 参数。
*   它允许在单个参数的帮助下向一个方法传递多个值。
*   它还可以存储重复的元素。

#### 构造器

| 构造器 | 描述 |
| **[元组<T1>(T1)](https://www.geeksforgeeks.org/how-to-create-1-tuple-or-singleton-tuple-in-c-sharp/# Using%20Tuple%3CT1%3E(T1)%20Constructor)T3】** | 初始化元组<t1>类的新实例。</t1> |

#### 财产

| 财产 | 描述 |
| **[第 1 项](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/)** | 获取元组<t1>对象的单个元素的值。</t1> |

**示例:**

```cs
// C# program to illustrate the constructor 
// and property of class Tuple<T1>
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 1-Tuple
        // Using Tuple<T1>(T1)
        Tuple<int> mytuple = new Tuple<int>(22);

        // Accessing the values
        Console.WriteLine("Value of the Element is: " + mytuple.Item1);
    }
}
```

**Output:**

```cs
Value of the Element is: 22

```

#### 方法

| 方法 | 描述 |
| **[等于(对象)](https://www.geeksforgeeks.org/c-sharp-check-if-two-tuple-objects-are-equal/)** | 返回一个值，该值指示当前元组<t1>对象是否等于指定对象。</t1> |
| **[GethashCode（）](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-of-the-tuple/)** | 返回当前元组<t1>对象的哈希代码。</t1> |
| **[【gettype()](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-tuples-element/)** | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **ToString()** | 返回表示该元组<t1>实例的值的字符串。</t1> |

**示例:**

```cs
// C# program to determine the 
// given tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 1-Tuple
        // Using Tuple<T1>(T1)
        Tuple<int> mytuple1 = new Tuple<int>(22);
        Tuple<int> mytuple2 = new Tuple<int>(22);

        // Using Equals method
        if (mytuple1.Equals(mytuple2))
        {
            Console.WriteLine("Tuple Matched..");
        }

        else
        {
            Console.WriteLine("Tuple not matched..");
        }
    }
}
```

**Output:**

```cs
Tuple Matched..

```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-1?视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-1?view=netframework-4.8)