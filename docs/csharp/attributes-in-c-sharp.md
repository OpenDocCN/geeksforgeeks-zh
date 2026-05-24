# c# 中的属性

> 原文:[https://www.geeksforgeeks.org/attributes-in-c-sharp/](https://www.geeksforgeeks.org/attributes-in-c-sharp/)

属性在 C# 中用于传达关于各种代码元素(如方法、程序集、属性、类型等)的声明性信息或元数据。通过使用声明性标记将属性添加到代码中，该标记使用方括号([ ])放置在所需代码元素的顶部。*提供了两种类型的属性实现。NET 框架*有:

*   **预定义的属性***   **Custom Attributes

    **属性属性:**

    *   属性可以像方法、属性等一样有参数。可以有争论。
    *   属性可以有零个或多个参数。
    *   不同的代码元素，如方法、程序集、属性、类型等。可以有一个或多个属性。
    *   反射可用于通过在运行时访问属性来获取程序的元数据。
    *   属性一般来源于**系统。属性类**。

    ### 1.预定义的属性

    预定义属性是属于。NET 框架类库，并且由 C# 编译器支持用于特定目的。从*系统导出的一些预定义属性。属性*基类给出如下:

    | 属性 | 描述 |
    | 属性 UsageAttribute | 此属性指定不同属性的用法。 |
    | CLSCompliantAttribute | 此属性显示特定代码元素是否符合公共语言规范。 |
    | contextstationattribute | 此属性指示静态字段值对于指定的上下文是否唯一。 |
    | 标志属性 | 此属性指示静态字段值对于指定的上下文是否唯一。 |
    | LoaderOptimizationAttribute | 此属性设置主方法中默认加载程序的优化策略。 |
    | 非序列化属性 | 此属性表示不应序列化可序列化类的字段。 |
    | ObsoleteAttribute | 该属性标记过时的代码元素，即不再使用的代码元素。 |
    | SerializableAttribute | 此属性表示可序列化类的字段可以序列化。 |
    | threadstationattribute | 该属性表示每个线程都有一个唯一的静态字段值。 |
    | DllImportAttribute | 此属性指示该方法是一个静态入口点，如非托管 DLL 所示。 |

    让我们讨论一些预定义的属性:

    #### CLSCompliantAttribute

    此属性显示特定代码元素是否符合公共语言规范。如果特定的代码元素符合公共语言规范。如果没有，编译器会发出警告消息。

    **例 1:** 这里，它不会给出任何警告消息，代码编译成功。

    ```cs
    // C# program to demonstrate CLSCompliantAttribute
    using System;

    // CLSCompliantAttribute applied to entire assembly
    [assembly:CLSCompliant(true)]

        public class GFG {

        // Main Method
        public static void Main(string[] args)
        {
            Console.WriteLine("GeeksForGeeks");
        }
    }
    ```

    **Output:**

    ```cs
    GeeksForGeeks

    ```

    **示例 2:** 这段代码将由编译器给出一条警告消息。

    ```cs
    // C# program to demonstrate CLSCompliantAttribute
    // giving a warning message
    using System;

    // CLSCompliantAttribute applied to entire assembly
    [assembly:CLSCompliant(true)]

        public class GFG {
        public uint z;
    }

    class GFG2 {

    // Main Method
    public static void Main(string[] args)
    {
        Console.WriteLine("GeeksForGeeks");
    }

    }
    ```

    **警告:**

    > prog.cs(9，14):警告 cs 3003:` gfg . z '类型不符合 CLS 标准

    #### 标志属性

    标志属性指定枚举可以用作一组标志。这最常用于按位运算符。

    **示例:**

    ```cs
    // C# program to demonstrate FlagsAttribute
    using System;

    class GFG {

        // Enum defined without FlagsAttribute.
        enum Colours { Red = 1,
                       Blue = 2,
                       Pink = 4,
                       Green = 8
        }

        // Enum defined with FlagsAttribute.
        [Flags] enum ColoursFlags { Red = 1,
                                    Blue = 2,
                                    Pink = 4,
                                    Green = 8
        }

        // Main Method
        public static void Main(string[] args)
        {
            Console.WriteLine((Colours.Red | Colours.Blue).ToString());
            Console.WriteLine((ColoursFlags.Red | ColoursFlags.Blue).ToString());
        }
    }
    ```

    **Output:**

    ```cs
    3
    Red, Blue

    ```

    #### ObsoleteAttribute

    ObsoleteAttribute 标记过时的代码元素，即不再使用的代码元素。调用这些过时的代码元素会导致编译器错误。

    **示例:**

    ```cs
    // C# program to demonstrate ObsoleteAttribute
    using System;

    class GFG {

        // The method1() is marked as obsolete
        [Obsolete("method1 is obsolete", true)] static void method1()
        {
            Console.WriteLine("This is method1");
        }

        static void method2()
        {
            Console.WriteLine("This is method2");
        }

        public static void Main(string[] args)
        {
            method1(); // Compiler error as method1() is obsolete
            method2();
        }
    }
    ```

    **编译错误:**

    > prog.cs(18，3):错误 CS0619: `GFG.method1()'已过时:` method1 已过时'

    ### 自定义属性

    可以在 C# 中创建自定义属性，用于将声明性信息附加到方法、程序集、属性、类型等。以任何需要的方式。这增加了。NET 框架。

    *创建自定义属性的步骤:*

    *   定义从*系统派生的自定义属性类。属性*类。
    *   自定义属性类名应该有后缀**属性**。
    *   使用属性属性用法指定创建的自定义属性类的用法。
    *   Create the constructor and the accessible properties of the custom attribute class.

        **示例:**

        ```cs
        // C# program to demonstrate Custom Attributes
        using System;

        // AttributeUsage specifies the usage
        // of InformationAttribute
        [AttributeUsage(AttributeTargets.Class | AttributeTargets.Constructor | 
                                AttributeTargets.Method, AllowMultiple = true)]

            // InformationAttribute is a custom attribute class
            // that is derived from Attribute class
            class InformationAttribute : Attribute
            {
                public string InformationString{ get; set; }
            }

        // InformationAttribute is used in student class
        [Information(InformationString = "Class")] public class student
        {

            private int rollno;
            private string name;

            [Information(InformationString = "Constructor")] public student(int rollno, string name)
            {
                this.rollno = rollno;
                this.name = name;
            }

            [Information(InformationString = "Method")] public void display()
            {
                Console.WriteLine("Roll Number: {0}", rollno);
                Console.WriteLine("Name: {0}", name);
            }
        }

        // Driver Class
        public class GFG {

            // Main Method
            public static void Main(string[] args)
            {
                student s = new student(1001, "Lily Adams");
                s.display();
            }
        }
        ```

        **Output:**

        ```cs
        Roll Number: 1001
        Name: Lily Adams

        ```**