# C# | Tuple

> 原文:[https://www.geeksforgeeks.org/c-sharp-tuple/](https://www.geeksforgeeks.org/c-sharp-tuple/)

单词 Tuple 的意思是“由多个部分组成的数据结构”。因此，元组是一种数据结构，它为您提供了最简单的方式来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。它 ***引入于。NET Framework 4.0*** 。在元组*中，您可以添加 1 到 8 个元素*。如果您试图添加大于 8 的元素，那么编译器将抛出一个错误。当您想要创建一个包含对象及其属性的数据结构，并且不想为其创建单独的类型时，通常使用元组。

**元组的特征:**

*   它允许我们将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用*输出*参数。
*   它还可以存储重复的元素。
*   它允许我们在单个参数的帮助下将多个值传递给一个方法。

#### C# 元组的需求是什么？

在元组之前，我们有三种方法从 C# 中的方法返回多个值，它们是*使用类或结构*类型、*输出参数*和*匿名类型，它们通过动态返回类型*返回。但是在元组之后，表示一组数据变得很容易。

出于另一个原因，想象一下这样一种情况，您希望将某个*员工*的详细信息存储在一个实体中，如姓名、EmpID、血型、联系号码。现在想到的最常见的方法是创建一个包含所需字段的数据结构。这就是元组发挥作用的地方。使用元组，不需要创建任何单独的数据结构。相反，对于这种情况，您可以使用*元组< T1、T2、T3、T4 >* 。

最常见的数据结构如数组、列表等。只属于特定类型，可以存储无限个元素。但是元组能够存储有限数量的元素，即 *8* ，并且可以是任何类型。

#### 创建元组

在 C# 中，创建元组的方式主要有以下两种:

*   **Using Constructor of Tuple Class:** You can create a tuple by using the constructor which is provided by **Tuple<T> class**. Where you can store elements starting from one to eight with their type. But you are not allowed to store elements greater than eight in a tuple. If you try to do so then the compiler will throw an error.

    **语法:**

    ```cs
    // Constructor for single elements
    Tuple <T1>(T1)

    // Constructor for two elements
    Tuple <T1, T2>(T1, T2)
    .
    .
    .
     // Constructor for eight elements
    Tuple <T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)
    ```

    **示例:**

    ```cs
    // C# program to create tuple using tuple constructor.
    using System;

    public class GFG{

        // Main method
        static public void Main (){

            // Tuple with one element
        Tuple<string>My_Tuple1 = new Tuple<string>("GeeksforGeeks");

        // Tuple with three elements
        Tuple<string, string, int>My_Tuple2 = new Tuple<string, string, int>("Romil", "Python", 29);

        // Tuple with eight elements
        Tuple<int, int, int, int, int, int, int, Tuple<int>>My_Tuple3 = new Tuple<int, int, int, int, int, int, int, Tuple<int>>(1,2,3,4,5,6,7, new Tuple<int>(8));
        }
    }
    ```

*   **Using Create Method:** When we use the tuple constructor to create a tuple we need to provide the type of each element stored in the tuple which makes your code cumbersome. So, C# provides another class that is Tuple class which contains the static methods for creating tuple object without providing the type of each element.

    **语法:**

    ```cs
    // Method for 1-tuple
    Create(T1)

    // Method for 2-tuple
    Create(T1, T2)
    .
    .
    .
    // Method for 8-tuple
    Create(T1, T2, T3, T4, T5, T6, T7, T8)

    ```

    **示例:**

    ```cs
    // C# program to create tuple 
    // using Create Method
    using System;

    public class GFG {

        // Main method
        static public void Main()
        {

            // Creating 1-tuple
            // Using Create Method
            var My_Tuple1 = Tuple.Create("GeeksforGeeks");

            // Creating 4-tuple
            // Using Create Method
            var My_Tuple2 = Tuple.Create(12, 30, 40, 50);

            // Creating 8-tuple
            // Using Create Method
            var My_Tuple3 = Tuple.Create(13, "Geeks", 67, 
                          89.90, 'g', 39939, "geek", 10);
        }
    }
    ```

    #### 访问元组

    您可以通过使用*项<元素号>属性*来访问元组的元素，这里的元素号是从 1 到 7，如项目 1、项目 2、项目 3、项目 4、项目 5、项目 6、项目 7 等。使用 Rest 属性可以访问 8 元组的最后一个元素。如下例所示:

    **示例:**

    ```cs
    // C# program to access the tuple 
    // using Item and Rest property
    using System;

    public class GFG {

        // Main method
        static public void Main()
        {

            // Creating 1-tuple
            // Using Create Method
            var My_Tuple1 = Tuple.Create("GeeksforGeeks");

            // Accessing the element of Tuple
            // Using Item property
            Console.WriteLine("Element of My_Tuple1: " + My_Tuple1.Item1);
            Console.WriteLine();

            // Creating 4-tuple
            // Using Create Method
            var My_Tuple2 = Tuple.Create(12, 30, 40, 50);

            // Accessing the element of Tuple
            // Using Item property
            Console.WriteLine("Element of My_Tuple2: " + My_Tuple2.Item1);
            Console.WriteLine("Element of My_Tuple2: " + My_Tuple2.Item2);
            Console.WriteLine("Element of My_Tuple2: " + My_Tuple2.Item3);
            Console.WriteLine("Element of My_Tuple2: " + My_Tuple2.Item4);
            Console.WriteLine();

            // Creating 8-tuple
            // Using Create Method
            var My_Tuple3 = Tuple.Create(13, "Geeks",
                  67, 89.90, 'g', 39939, "geek", 10);

            // Accessing the element of Tuple
            // Using Item property
            // And print the 8th element of tuple
            // using Rest property
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Item1);
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Item2);
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Item3);
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Item4);
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Item5);
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Item6);
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Item7);
            Console.WriteLine("Element of My_Tuple3: " + My_Tuple3.Rest);
        }
    }
    ```

    **输出:**

    ```cs
    Element of My_Tuple1: GeeksforGeeks

    Element of My_Tuple2: 12
    Element of My_Tuple2: 30
    Element of My_Tuple2: 40
    Element of My_Tuple2: 50

    Element of My_Tuple3: 13
    Element of My_Tuple3: Geeks
    Element of My_Tuple3: 67
    Element of My_Tuple3: 89.9
    Element of My_Tuple3: g
    Element of My_Tuple3: 39939
    Element of My_Tuple3: geek
    Element of My_Tuple3: (10)

    ```

    #### 嵌套元组

    在 C# 中，您可以在另一个元组中创建一个元组。当您想要在同一个元组中添加八个以上的元素时，可以使用嵌套元组。嵌套元组可以通过使用 Rest 属性来访问，如示例 1 所示。您可以在序列的任何地方添加嵌套元组，但是建议您可以将嵌套元组放在序列的末尾，以便它们可以从 Rest 属性轻松访问。如果将嵌套元组放置在最后一个位置之外，则可以根据 Item <elementnumber>属性访问元组，如示例 2 所示。</elementnumber>

    **例 1:**

    ```cs
    // C# program to illustrate nested tuple
    using System;

    public class GFG{

            // Main method
        static public void Main ()
            {

               // Nested Tuple
            var My_Tuple = Tuple.Create(13, "Geeks", 67, 89.90,
                     'g', 39939, "geek", Tuple.Create(12, 30, 40, 50));

            // Accessing the element of Tuple
            // Using Item property
            // And accessing the elements of nested tuple
            // Using Rest property
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item1);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item2);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item3);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item4);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item5);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item6);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item7);
            Console.WriteLine("Element of Nested tuple: "+My_Tuple.Rest);
            Console.WriteLine("Element of Nested tuple: "+My_Tuple.Rest.Item1.Item1);
            Console.WriteLine("Element of Nested tuple: "+My_Tuple.Rest.Item1.Item2);
            Console.WriteLine("Element of Nested tuple: "+My_Tuple.Rest.Item1.Item3);
            Console.WriteLine("Element of Nested tuple: "+My_Tuple.Rest.Item1.Item4);
        }
    }
    ```

    **输出:**

    ```cs
    Element of My_Tuple: 13
    Element of My_Tuple: Geeks
    Element of My_Tuple: 67
    Element of My_Tuple: 89.9
    Element of My_Tuple: g 
    Element of My_Tuple: 39939
    Element of My_Tuple: geek
    Element of Nested tuple: ((12, 30, 40, 50))
    Element of Nested tuple: 12
    Element of Nested tuple: 30
    Element of Nested tuple: 40
    Element of Nested tuple: 50

    ```

    **例 2:**

    ```cs
    // C# program to illustrate nested tuple
    using System;

    public class GFG{

            // Main method
        static public void Main ()
            {

               // Nested Tuple
               // Here nested tuple is present 
                   // at the place of 2nd element
            var My_Tuple = Tuple.Create(13, Tuple.Create(12, 30, 40,
                                   50),67, 89.90, 'g', 39939, 123, "geeks");

            // Accessing the element of Tuple
            // Using Item property
            // And accessing the elements of 
            // nested tuple Using Rest property
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item1);
            Console.WriteLine("Element of Nested Tuple: "+My_Tuple.Item2.Item1);
            Console.WriteLine("Element of Nested Tuple: "+My_Tuple.Item2.Item2);
            Console.WriteLine("Element of Nested Tuple: "+My_Tuple.Item2.Item3);
            Console.WriteLine("Element of Nested Tuple: "+My_Tuple.Item2.Item4);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item3);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item4);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item5);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item6);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Item7);
            Console.WriteLine("Element of My_Tuple: "+My_Tuple.Rest);

        }
    }
    ```

    **输出:**

    ```cs
    Element of My_Tuple: 13
    Element of Nested Tuple: 12
    Element of Nested Tuple: 30
    Element of Nested Tuple: 40
    Element of Nested Tuple: 50
    Element of My_Tuple: 67
    Element of My_Tuple: 89.9
    Element of My_Tuple: g
    Element of My_Tuple: 39939
    Element of My_Tuple: 123
    Element of My_Tuple: (geeks)
    ```

    #### 元组作为方法参数

    在 C# 中，您可以将元组作为方法参数传递，如下例所示。在这里，我们在*print tuple()*方法中传递一个名为 *mytuple* 的元组，并使用 Item < elementNumber >属性访问该元组的元素。

    **示例:**

    ```cs
    // C# program to illustrate the 
    // tuple as a method parameter.
    using System;

    public class GFG{

            // Main method
        static public void Main ()
            {

                // Creating a tuple 
            var mytuple = Tuple.Create("GeeksforGeeks", 123, 90.8);

            // Pass the tuple in the
                    // PrintTheTuple method
            PrintTheTuple(mytuple);
        }

        static void PrintTheTuple(Tuple<string, int, double>mytuple)
            {
            Console.WriteLine("Element: "+mytuple.Item1);
            Console.WriteLine("Element: "+mytuple.Item2);
            Console.WriteLine("Element: "+mytuple.Item3);
        }
    }
    ```

    **输出:**

    ```cs
    Element: GeeksforGeeks
    Element: 123
    Element: 90.8

    ```

    #### 作为返回类型的元组

    在 C# 中，允许方法使用元组作为返回类型。或者换句话说，方法可以返回元组，如下例所示:

    **示例:**

    ```cs
    // C# program to illustrate 
    // how a method return tuple
    using System;

    public class GFG{

            // Main Method
        static public void Main ()
            {
                // Return tuple is stored in mytuple
            var mytuple = PrintTuple();
            Console.WriteLine(mytuple.Item1);
            Console.WriteLine(mytuple.Item2);
            Console.WriteLine(mytuple.Item3);
        }

        // PrintTuple method return a tuple 
        static Tuple<string, string, string>PrintTuple()
            {
            return Tuple.Create("Geeks", "For", "Geeks");
        }
    }
    ```

    **输出:**

    ```cs
    Geeks
    For
    Geeks

    ```

    **元组的限制:**

    *   它属于引用类型，而不是值类型。
    *   它仅限于八个元素。意味着没有嵌套元组，您不能存储超过八个元素。
    *   这些只能通过使用*项目<元素编号>属性*来访问。