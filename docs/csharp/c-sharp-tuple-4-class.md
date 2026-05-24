# C# | Tuple <t1>类</t1>T3】

> 原文:[https://www.geeksforgeeks.org/c-sharp-tuple-4-class/](https://www.geeksforgeeks.org/c-sharp-tuple-4-class/)

元组<t1 t2="" t3="" t4="">类用于创建一个 4 元组或四元组。它表示一个包含四个元素的元组。您可以通过调用 [**元组< T1、T2、T3、T4 > (T1、T2、T3、T4)构造函数**](https://www.geeksforgeeks.org/how-to-create-4-tuple-or-quadruple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4%3E(T1,%20T2,%20T3,%20T4)%20Constructor) 或静态 [**元组来实例化元组<t1 t2="" t3="" t4="">对象。创建</t1>**](https://www.geeksforgeeks.org/how-to-create-4-tuple-or-quadruple-in-c-sharp/# Using%20the%20Create%20method) 方法。您可以使用只读的*项目 1* 、*项目 2* 、*项目 3* 和*项目 4* 实例属性来检索元组元素的值。
**要点:**</t1>

*   它实现了*结构可比较*、*结构可比较*、*我可比较*接口。
*   它是在系统命名空间下定义的。
*   它将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用 out 参数。
*   它允许在单个参数的帮助下向一个方法传递多个值。
*   它还可以存储重复的元素。

#### 构造器

。元组-类-表{边框-折叠:折叠；宽度:100%；} .元组类表 td {边框:1px 实心# 5fb962 文本对齐:向左！重要；填充:8px} .tuple-class-table th { border:1px solid # 5fb 962；填充:8px} .tuple-class-table tr>th{底色:# c6ebd9 垂直对齐:中间；} .元组类表 tr:第 n 个子(奇数){背景色:# ffffff}

<figure class="table">

| 构造器 | 描述 |
| [**元组< T1、T2、T3、T4 > (T1、T2、T3、T4)**](https://www.geeksforgeeks.org/how-to-create-4-tuple-or-quadruple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4%3E(T1,%20T2,%20T3,%20T4)%20Constructor) | 初始化元组<t1 t2="" t3="" t4="">类的新实例。</t1> |

</figure>

#### 财产

<figure class="table">

| 财产 | 描述 |
| [**第 1 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/) | 获取元组<t1 t2="" t3="" t4="">对象的第一个分量的值。</t1> |
| [**第 2 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-second-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="">对象的第二个分量的值。</t1> |
| [**第 3 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-third-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="">对象的第三个分量的值。</t1> |
| [**第 4 项**](https://www.geeksforgeeks.org/c-sharp-how-to-get-fourth-element-of-the-tuple/) | 获取当前元组<t1 t2="" t3="" t4="">对象的第四个分量的值。</t1> |

</figure>

**示例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the constructor
// and property of Tuple<T1, T2, T3, T4> Class
using System;

class GFG {

    // Main Method
    static public void Main ()
    {
        // Creating 4-Tuple
        // Using Tuple<T1, T2, T3,
        // T4>(T1, T2, T3, T4) constructor
        Tuple<int, int, int, string>mytuple = new Tuple<int,
                     int, int, string>(79, 34, 67, "Geeks");

        // Accessing the values
        Console.WriteLine("Value of the First Component: " + mytuple.Item1);
        Console.WriteLine("Value of the Second Component: " + mytuple.Item2);
        Console.WriteLine("Value of the Third Component: " + mytuple.Item3);
        Console.WriteLine("Value of the Fourth Component: " + mytuple.Item4);

    }
}
```

**Output:** 

```cs
Value of the First Component: 79
Value of the Second Component: 34
Value of the Third Component: 67
Value of the Fourth Component: Geeks
```

#### 方法

<figure class="table">

| 方法 | 描述 |
| [**等于(对象)**](https://www.geeksforgeeks.org/c-sharp-check-if-two-tuple-objects-are-equal/) | 返回一个值，该值指示当前元组<t1 t2="" t3="" t4="">对象是否等于指定对象。</t1> |
| [**GethashCode（）**](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-of-the-tuple/) | 返回当前元组<t1 t2="" t3="" t4="">对象的哈希代码。</t1> |
| [**【gettype()**](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-tuples-element/) | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **ToString()** | 返回表示该元组<t1 t2="" t3="" t4="">实例的值的字符串。</t1> |

</figure>

**示例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to check whether the
// given tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 4-Tuple
        // Using Tuple<T1, T2, T3, T4>(T1,
        // T2, T3, T4) constructor
        Tuple<int, int, int, int> mytuple1 = new Tuple<int,
                            int, int, int>(20, 40, 90, 89);

        Tuple<int, int, int, int> mytuple2 = new Tuple<int,
                            int, int, int>(20, 40, 90, 89);

        // Using Equals method
        if (mytuple1.Equals(mytuple2))
        {
            Console.WriteLine("Tuple Matched..");
        }

        else
        {
            Console.WriteLine("Tuple not Matched..");
        }
    }
}
```

**Output:** 

```cs
Tuple Matched..
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-4?视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-4?view=netframework-4.8)