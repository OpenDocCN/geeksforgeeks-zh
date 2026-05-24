# c# 中的 value tuple

> 原文:[https://www.geeksforgeeks.org/valuetuple-in-c-sharp/](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/)

ValueTuple 是 C# 7.0 中引入的一个结构，它表示值类型 [Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/) 。它已经包含在*中。NET Framework 4.7* 或更高版本。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。它可以存储从 0 到 8 的元素，也可以存储不同类型的元素。您也可以在值元组中存储重复的元素。

#### 为什么我们需要 ValueTuple？

我们在 C# 中已经有了 **[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)** ，用来存储多个值，但是元组有一些限制，这些限制在 ValueTuple 中是固定的。或者我们可以说 *ValueTuple 是 C#* 中元组的改进版本。它克服了元组的以下限制:

*   元组属于引用类型，但值元组属于值类型。
*   Tuple 不提供命名约定，但是 ValueTuple 提供了强命名约定。
*   在元组中，不允许创建一个零元素的元组，但是在值元组中，允许创建一个零元素的元组。
*   ValueTuple 的性能优于 Tuple。因为 ValueTuple 为从现有方法返回多个值提供了一种轻量级机制。并且 ValueTuple 的语法比元组更优化。
*   ValueTuple 通过使用解构和 **_ 关键字**，为访问值元组的元素提供了更多的灵活性。但是 Tuple 不能提供解构的概念和 _ 关键字。
*   在 ValueTuple 中，像 item1 和 item2 这样的成员是字段。但是在 Tuple 中，它们是属性。
*   在 ValueTuple 中，字段是可变的。但是在 Tuple 中，字段是只读的。

#### 创建值元组

与元组不同，值元组提供了一种创建和初始化值元组的简单机制。您可以使用以下 **3** 方式创建值元组:

*   **Using Constructor:** You can create ValueTuple by using the constructor provided by the ValueTuple<T> Struct. Where you can store elements starting from one to eight with their type.

    **语法:**

    ```cs
    // Constructor for creating one element
    ValueTuple<T1>(T1)

    // Constructor for creating two elements
    ValueTuple<T1, T2>(T1, T2)
    .
    .
    .

    // Constructor for creating eight elements
    ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)    

    ```

    **示例:**

    ```cs
    // C# program to illustrate how to
    // create value tuple using the 
    // ValueTuple constructor.
    using System;

    class GFG {

        // Main method
        static public void Main()
        {

            // ValueTuple with one element
            ValueTuple<int> ValTpl1 = new ValueTuple<int>(345678);

            // ValueTuple with three elements
            ValueTuple<string, string, int> ValTpl2 = new ValueTuple<string,
                                            string, int>("C#", "Java", 586);

            // ValueTuple with eight elements
            ValueTuple<int, int, int, int, int, int, int, ValueTuple<int> > ValTpl3 = new ValueTuple<int,
                                      int, int, int, int, int, int, ValueTuple<int> >(45, 67, 65, 34, 34,
                                                                        34, 23, new ValueTuple<int>(90));
        }
    }
    ```

*   **Using Create Method:** When we use the constructor of ValueTuple<T> struct to create a value tuple we need to provide the type of each element stored in the value tuple which makes your code cumbersome. So, C# provides another ValueTuple struct which contains the static methods for creating value tuple object without providing the type of each element.

    **语法:**

    ```cs
    // Method for creating an empty value tuple
    Create();

    // Method for creating 1-ValueTuple
    Create<T1>(T1)
    .
    .
    .

    // Method for creating 8-ValueTuple
    Create<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, T8)

    ```

    **示例:**

    ```cs
    // C# program to create value tuple
    // using Create Method
    using System;

    public class GFG {

        // Main method
        static public void Main()
        {

            // Creating 0-ValueTuple
            // Using Create() Method
            var Valtpl1 = ValueTuple.Create();

            // Creating 3-ValueTuple
            // Using Create(T1, T2, T3) Method
            var Valtpl2 = ValueTuple.Create(12, 30, 40, 50);

            // Creating 8-ValueTuple
            // Using Create(T1, T2, T3, T4, T5, T6, T7, T8) Method
            var Valtpl3 = ValueTuple.Create(34, "GeeksforGeks", 
                          'g', 'f', 'g', 56.78, 4323, "geeks");
        }
    }
    ```

*   **使用括号():**这是使用括号()创建 value 元组的最简单形式，元素放在它们之间。元素以不同的方式存储在 **2** 中:
    *   **Named Member:** ValueTuple allows you to create a tuple in which each component is allowed to have their own name. So that you can access that component with the help of their name. It makes your program more readable and easy to remember. You can assign the names to the members either left-hand side or right-hand, but not both sides. If you assigned names to both sides, then the left-hand side has precedence over the right-hand side As shown below:

        **例 1:**

        ```cs
        // C# program to illustrated named member
        using System;

        public class GFG {
            static public void Main()
            {
                (int age, string Aname, string Lang) author = (23, "Sonia", "C#");
            }
        }
        ```

        **例 2:**

        ```cs
        // C# program to illustrated named member
        using System;

        public class GFG {

            static public void Main()
            {
                var author = (age : 23, Aname
                              : "Sonia", Lang
                              : "C#");
            }
        }
        ```

    *   **UnNamed Member:** In ValueTuples, the unnamed members are those members which does not have names. They are simply created without any name. As shown below:

        **例 1:**

        ```cs
        // C# program to illustrated UnNamed member
        using System;

        public class GFG {
            static public void Main()
            {
                var author = (20, "Siya", "Ruby");
            }
        }
        ```

        **例 2:**

        ```cs
        // C# program to illustrated UnNamed member
        using System;

        public class GFG {
            static public void Main()
            {
                ValueTuple<int, string, string> author = (20, "Siya", "Ruby");
            }
        }
        ```

#### 访问 ValueTuple 成员

这里我们学习如何访问 value 元组的命名和未命名成员。

*   **Accessing unnamed members:** In ValueTuple, unnamed members are accessible by using the default item property names like Item1, Item2, Item3, etc. As shown in the below example:

    **示例:**

    ```cs
    // C# program to illustrate how to 
    // access unnamed members of ValueTuple
    using System;

    public class GFG {

        // Main Method
        static public void Main()
        {

            // ValueTuple with three elements
            var author = (20, "Siya", "Ruby");

            // Accessing the ValueTuple
            // Using default Item property
            Console.WriteLine("Age:" + author.Item1);
            Console.WriteLine("Name:" + author.Item2);
            Console.WriteLine("Language:" + author.Item3);
        }
    }
    ```

*   **Accessing Named members:** In ValueTuples, the named members are used according to their name. There is no need to access these named members with default item property. As shown in the below example, the ValueTuple contains three elements, i.e, Book_id, Author_name, and Book_name. And we directly access these elements according to their names.

    **示例:**

    ```cs
    // C# program to illustrate how to access
    // named members of ValueTuple
    using System;

    public class GFG {

        // Main Method
        static public void Main()
        {

            // ValueTuple with three elements
            var library = (Book_id : 2340, Author_name
                           : "Arundhati Roy", Book_name
                           : "The God of Small Things");

            // Accessing the ValueTuple
            // according to their names
            Console.WriteLine("Book Id: {0}", library.Book_id);
            Console.WriteLine("Author Name: {0}", library.Author_name);
            Console.WriteLine("Book Name: {0}", library.Book_name);
        }
    }
    ```

    **输出:**

    ```cs
    Book Id: 2340
    Author Name: Arundhati Roy
    Book Name: The God of Small Things

    ```

#### 返回值元组

在 C# 中，您可以从方法中返回一个 ValueTuple。如下例所示，TouristDetails 方法返回一个包含 3 个元素的 ValueTuple:

**示例:**

```cs
// C# program to illustrate how a
// method return ValueTuple
using System;

public class GFG {

    // This method returns the tourist details
    static(int, string, string) TouristDetails()
    {
        return (384645, "Sophite", "USA");
    }

    // Main method
    static public void Main()
    {

        // Store the data provided by the TouristDetails method
        var(Tourist_Id, Tourist_Name, Country) = TouristDetails();

        // Display data
        Console.WriteLine("Tourist Details: ");
        Console.WriteLine($ "Tourist Id: {Tourist_Id}");
        Console.WriteLine($ "Tourist Name: {Tourist_Name}");
        Console.WriteLine($ "Country: {Country}");
    }
}
```

**输出:**

```cs
Tourist Details: 
Tourist Id: 384645
Tourist Name: Sophite
Country: USA

```