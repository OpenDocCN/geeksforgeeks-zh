# C# | Tuple <t1>类</t1>T3】

> 原文:[https://www.geeksforgeeks.org/c-sharp-tuple-8-class/](https://www.geeksforgeeks.org/c-sharp-tuple-8-class/)

元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">类用于创建 n = 8 或大于 8 的 n 元组。它表示包含八个或八个以上元素的元组。您可以通过调用 [**元组< T1、T2、T3、T4、T5、T6、T7、TRest > (T1、T2、T3、T4、T5、T6、T7、TRest)构造函数**](https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4,T5,T6,T7,TRest%3E(T1,%20T2,%20T3,%20T4,%20T5,%20T6,%20T7,%20TRest)%20Constructor) 或静态 [**元组来实例化元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象。创建</t1>**](https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/# Using%20the%20Create%20method) 方法。您可以使用只读的*项目 1* 、*项目 2* 、*项目 3* 、*项目 4* 、*项目 5* 、*项目 6* 、*项目 7* 和 *Rest* 实例属性来检索元组元素的值。</t1>

**要点:**

*   它实现了*结构可比较*、*结构可比较*和*我可比较*接口。
*   它是在系统命名空间下定义的。
*   借助嵌套，您可以在一个元组中创建八个以上的元素。您可以在元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">中的 Rest 参数处创建一个嵌套元组。</t1>
*   它将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用 out 参数。
*   它允许在单个参数的帮助下向一个方法传递多个值。
*   它还可以存储重复的元素。

#### 构造器

<figure class="table">

| 构造器 | 描述 |
| --- | --- |
| [**元组< T1、T2、T3、T4、T5、T6、T7、TRest > (T1、T2、T3、T4、T5、T6、T7、TRest)**](https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4,T5,T6,T7,TRest%3E(T1,%20T2,%20T3,%20T4,%20T5,%20T6,%20T7,%20TRest)%20Constructor) | 初始化元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">类的新实例。</t1> |

</figure>

#### 财产

<figure class="table">

| 财产 | 描述 |
| --- | --- |
| [**第 1 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/) | 获取元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的第一个元素的值。</t1> |
| [**第 2 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-second-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的第二个元素的值。</t1> |
| [**第 3 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-third-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的第三个元素的值。</t1> |
| [**第 4 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-fourth-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的第四个元素的值。</t1> |
| [**第 5 项**](https://www.geeksforgeeks.org/c-sharp-sharp-how-to-get-fifth-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的第五个元素的值。</t1> |
| [**第 6 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-sixth-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的第六个元素的值。</t1> |
| [**第 7 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-seventh-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的第七个元素的值。</t1> |
| [**休息**](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-remaining-elements-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的剩余元素。</t1> |

</figure>

**示例:**

## C#

```cs
// C# program to illustrate the constructor
// and property of Tuple<T1, T2, T3, T4,
// T5, T6, T7, TRest> Class
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Creating 8-Tuple
        // Using Tuple<T1, T2, T3, T4, T5, T6, T7,
        // TRest>(T1, T2, T3, T4, T5, T6, T7,
        // TRest) constructor
        Tuple<int, int, int, string, int, string, int, Tuple<int, int>> mytuple = new Tuple<int,
                   int, int, string, int, string, int, Tuple<int, int> >(79, 34, 67, "Geeks", 44,
                                               "GeeksforGeeks", 66, new Tuple<int, int>(89, 77));

       // Accessing the values
        Console.WriteLine("Value of the First Component: " + mytuple.Item1);
        Console.WriteLine("Value of the Second Component: " + mytuple.Item2);
        Console.WriteLine("Value of the Third Component: " + mytuple.Item3);
        Console.WriteLine("Value of the Fourth Component: " + mytuple.Item4);
        Console.WriteLine("Value of the Fifth Component: " + mytuple.Item5);
        Console.WriteLine("Value of the Sixth Component: " + mytuple.Item6);
        Console.WriteLine("Value of the Seventh Component: " + mytuple.Item7);
        Console.WriteLine("Value of the Eighth Component: " + mytuple.Rest);

    }
}
```

**Output:** 

```cs
Value of the First Component: 79
Value of the Second Component: 34
Value of the Third Component: 67
Value of the Fourth Component: Geeks
Value of the Fifth Component: 44
Value of the Sixth Component: GeeksforGeeks
Value of the Seventh Component: 66
Value of the Eighth Component: (89, 77)
```

#### 方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [**等于(对象)**](https://www.geeksforgeeks.org/c-sharp-check-if-two-tuple-objects-are-equal/) | 返回一个值，该值指示当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象是否等于指定对象。</t1> |
| [**GethashCode（）**](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-of-the-tuple/) | 返回当前元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">对象的哈希代码。</t1> |
| [**【gettype()**](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-tuples-element/) | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **ToString()** | 返回表示该元组<t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">实例的值的字符串。</t1> |

</figure>

**示例:**

## C#

```cs
// C# program to check whether the
// given tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 8-Tuple
        // Using Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1,
        // T2, T3, T4, T5, T6, T7, TRest) constructor
        Tuple<int, int, int, int, int, int, int, Tuple<string> > mytuple1 = new Tuple<int,
                                 int, int, int, int, int, int, Tuple<string> >(20, 40, 90,
                                       89, 33, 66, 87, new Tuple<string>("GeeksforGeeks"));

        Tuple<int, int, int, int, int, int, int, Tuple<string> > mytuple2 = new Tuple<int,
                                 int, int, int, int, int, int, Tuple<string> >(20, 40, 90,
                                      89, 33, 66, 87, new Tuple<string>("GeeksforGeeks"));

        // Using Equals method
        if (mytuple1.Equals(mytuple2))
        {
            Console.WriteLine("Tuple Matched.");
        }

        else
        {
            Console.WriteLine("Tuple Not Matched.");
        }
    }
}
```

**Output:** 

```cs
Tuple Matched.
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-8?视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-8?view=netframework-4.8)