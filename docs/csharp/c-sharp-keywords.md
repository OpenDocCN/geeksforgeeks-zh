# C# |关键词

> 原文:[https://www.geeksforgeeks.org/c-sharp-keywords/](https://www.geeksforgeeks.org/c-sharp-keywords/)

**关键词或保留词**是一种语言中用于某些内部过程或代表某些预定义动作的词。因此，这些词不允许用作变量名或对象。这样做会导致一个**编译时错误**。

**示例:**

```cs
// C# Program to illustrate the keywords
using System;

class GFG {

    // Here static, public, void 
    // are keywords    
    static public void Main () {

        // here int is keyword
        // a is identifier
        int a = 10;

        Console.WriteLine("The value of a is: {0}",a);

        // this is not a valid identifier

        // removing comment will give compile time error
        // double int = 10;

    }
}
```

**输出:**

```cs
The value of a is: 10
```

C# 中总共有 78 个关键字，如下所示:

| 摘要 |
| 如同 |
| 基础 |
| 弯曲件 |
| 破裂 |
| 字节 |
| 情况 |
| 捕捉 |
| 茶 |
| 检查 |
| 班级 |
| 常数 |
| 继续 |
| 小数 |
| 系统默认值 |
| 代表 |

| 做 |
| 两倍 |
| 其他 |
| 列举型别 |
| 事件 |
| 明确的 |
| 走读生 |
| 错误的 |
| 最后 |
| 固定的；不变的 |
| 漂浮物 |
| 为 |
| 为每一个 |
| 转到 |
| 如果 |
| 含蓄的 |

| 在 |
| （同 Internationalorganizations）国际组织 |
| 连接 |
| 内部的 |
| 是 |
| 锁 |
| 长的 |
| 命名空间 |
| 新的 |
| 空 |
| 目标 |
| 操作员 |
| 在外 |
| 推翻 |
| 参数 |
| 私人的 |

| 保护 |
| 公众的 |
| 只读的 |
| 裁判员 |
| 返回 |
| sbyte(字节) |
| 密封的 |
| 短的 |
| 西泽夫 |
| 斯戴克 |
| 静电 |
| 线 |
| 结构体 |
| 转换 |
| 这 |

| 扔 |
| 真实的 |
| 尝试 |
| 类型 |
| 单位 |
| 乌龙！乌龙 |
| 未加抑制的 |
| 危险的 |
| 乌肖特 |
| 使用 |
| 使用静态 |
| 虚拟的 |
| 空的 |
| 不稳定的 |
| 在…期间 |

**c# 中的关键词主要分为以下 10 类:**

1.  **Value Type Keywords:** There are **15** keywords in value types which are used to define various data types.

    | 弯曲件 | 字节 | 茶 | 小数 |
    | 两倍 | 列举型别 | 漂浮物 | （同 Internationalorganizations）国际组织 |
    | 长的 | sbyte(字节) | 短的 | 结构体 |
    | 单位 | 乌龙！乌龙 | 乌肖特 |  |

    **示例:**

    ```cs
    // C# Program to illustrate the
    // value type keywords
    using System;

    class GFG {

        // Here static, public, void 
        // are keywords    
        static public void Main () {

            // here byte is keyword
            // a is identifier
            byte a = 47;
            Console.WriteLine("The value of a is: {0}",a);

            // here bool is keyword
            // b is identifier
            // true is a keyword
            bool b = true;

            Console.WriteLine("The value of b is: {0}",b);

        }
    }
    ```

    **输出:**

    ```cs
    The value of a is: 47
    The value of b is: True

    ```

2.  **Reference Type Keywords:** There are **6** keywords in reference types which are used to store references of the data or objects. The keywords in this category are: ***class, delegate, interface, object, string, void***.
3.  **Modifiers Keywords:** There are **17** keywords in modifiers which are used to modify the declarations of type member.

    | 公众的 | 私人的 | 内部的 | 保护 | 摘要 |
    | 常数 | 事件 | 走读生 | 新的 | 推翻 |
    | 部分的 | 只读的 | 密封的 | 静电 | 危险的 |
    | 虚拟的 | 不稳定的 |  |  |  |

    **示例:**

    ```cs
    // C# Program to illustrate the
    // modifiers keywords
    using System;

    class Geeks {

        class Mod
        {

            // using public modifier
            // keyword
            public int n1;

        }

        // Main Method
        static void Main(string[] args) {

            Mod obj1 = new Mod();

            // access to public members
            obj1.n1 = 77;

            Console.WriteLine("Value of n1: {0}", obj1.n1);

        }

    }
    ```

    **输出:**

    ```cs
    Value of n1: 77
    ```

4.  **Statements Keywords:** There are total **18** keywords which are used in program instructions.

    | 如果 | 其他 | 转换 | 做 | 为 |
    | 为每一个 | 在 | 在…期间 | 破裂 | 继续 |
    | 转到 | 返回 | 扔 | 尝试 | 捕捉 |
    | 最后 | 检查 | 未加抑制的 |  |  |

    **示例:**

    ```cs
    // C# program to illustrate the statement keywords
    using System; 

    class demoContinue 
    { 
        public static void Main() 
        {     

            // using for as statement keyword
            // GeeksforGeeks is printed only 2 times 
            // because of continue statement 
            for(int i = 1; i < 3; i++) 
            { 

                // here if and continue are keywords
                if(i == 2) 
                continue; 

                Console.WriteLine("GeeksforGeeks"); 
            } 
        } 
    } 
    ```

    **输出:**

    ```cs
    GeeksforGeeks
    ```

5.  **Method Parameters Keywords:** There are total **4** keywords which are used to change the behavior of the parameters that passed to a method. The keyword includes in this category are: ***params, in, ref, out***.
6.  **Namespace Keywords:** There are total **3** keywords in this category which are used in [namespaces](https://www.geeksforgeeks.org/c-namespaces/). The keywords are: ***namespace, using, extern***.
7.  **Operator Keywords:** There are total **8** keywords which are used for different purposes like creating objects, getting a size of object etc. The keywords are: ***as, is, new, sizeof, typeof, true, false, stackalloc***.
8.  **Conversion Keywords:** There are **3** keywords which are used in type conversions. The keywords are: ***explicit, implicit, operator***.

9.  **Access Keywords:** There are **2** keywords which are used in accessing and referencing the class or instance of the class. The keywords are ***base, this***.
10.  **字面关键词:**有 **2** 关键词作为字面或常量使用。关键词为 ***空，默认*** 。

**要点:**

*   关键字不用作类、变量等的标识符或名称。
*   如果您想使用关键字作为标识符，那么您必须使用@作为前缀。例如，*@摘要*是有效标识，而不是*摘要*，因为它是关键字。

**示例:**

```cs
int a = 10;              // Here int is a valid keyword

double int = 10.67;     // invalid because int is a keyword

double @int = 10.67;   // valid identifier, prefixed with @

int @null = 0;       // valid

```

```cs
// C# Program to illustrate the use of 
// prefixing @ in keywords
using System;

class GFG {

    // Here static, public, void 
    // are keywords    
    static public void Main () {

        // here int is keyword
        // a is identifier
        int a = 10;

        Console.WriteLine("The value of a is: {0}",a);

        // prefix @ in keyword int which 
        // makes it a valid identifier
        int @int = 11;

        Console.WriteLine("The value of a is: {0}",@int);

    }
}
```

**输出:**

```cs
The value of a is: 10
The value of a is: 11

```

#### 上下文关键词

这些用来在程序中赋予特定的含义。每当一个新的关键字出现在 C# 中，它都会被添加到上下文关键字中，而不是关键字类别中。这有助于避免早期版本编写的程序崩溃。

**要点:**

*   这些不是保留词。
*   它可以用作上下文之外的标识符，这就是它命名上下文关键字的原因。
*   这些在两个或多个上下文中可能有不同的含义。
*   C# 中共有 **30** 个上下文关键词。

| 增加 |
| 别名 |
| 上升的 |
| 异步ˌ非同步(asynchronous) |
| 等待 |
| 经过 |
| 下降 |
| 动态的 |

| 等于 |
| 从 |
| 得到 |
| 全球的 |
| 组 |
| 到…里面 |
| 加入 |
| 让 |

| 的名称 |
| 在 |
| 排序依据 |
| 部分(类型) |
| 部分(方法) |
| 去除 |
| 挑选 |
| 设置 |

| 价值 |
| 定义变量 |
| 当...的时候 |
| 在哪里 |
| 在哪里 |
| 产量 |

**示例:**

```cs
// C# program to illustrate contextual keywords
using System; 

public class Student { 

    // Declare name field 
    private string name = "GeeksforGeeks"; 

    // Declare name property 
    public string Name 
    { 

    // get is contextual keyword
    get
        { 
            return name; 
        } 

        // set is a contextual
        // keyword
        set
        { 
            name = value; 
        } 
    } 
} 

class TestStudent { 

    // Main Method 
    public static void Main(string[] args) 
    { 
        Student s = new Student(); 

        // calls set accessor of the property Name, 
        // and pass "GFG" as value of the 
        // standard field 'value'. 
        s.Name = "GFG"; 

        // displays GFG, Calls the get accessor 
        // of the property Name. 
        Console.WriteLine("Name: " + s.Name); 

        // using get and set as identifier
        int get = 50;
        int set = 70;

        Console.WriteLine("Value of get is: {0}",get);
        Console.WriteLine("Value of set is: {0}",set);
    } 
} 
```

**输出:**

```cs
Name: GFG
Value of get is: 50
Value of set is: 70

```

**参考:**[https://docs . Microsoft . com/en-us/dotnet/csharp/language-Reference/keywords/](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/)