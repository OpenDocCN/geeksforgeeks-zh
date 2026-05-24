# C# 中的 ValueTuple

> 原文: [https://www.geeksforgeeks.org/valuetuple-in-c-sharp/](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/)

`ValueTuple` 是 C# 7.0 中引入的一个结构，它表示值类型 [Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)。它已经包含在 .NET Framework 4.7 或更高版本中。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。它可以存储从 0 到 8 的元素，也可以存储不同类型的元素。您也可以在值元组中存储重复的元素。

## 为什么我们需要 ValueTuple？

我们在 C# 中已经有了 [元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，用来存储多个值，但是元组有一些限制，这些限制在 `ValueTuple` 中是固定的。或者我们可以说 `ValueTuple` 是 C# 中元组的改进版本。它克服了元组的以下限制：

*   元组属于引用类型，但值元组属于值类型。
*   `Tuple` 不提供命名约定，但是 `ValueTuple` 提供了强命名约定。
*   在元组中，不允许创建一个零元素的元组，但是在值元组中，允许创建一个零元素的元组。
*   `ValueTuple` 的性能优于 `Tuple`。因为 `ValueTuple` 为从现有方法返回多个值提供了一种轻量级机制。并且 `ValueTuple` 的语法比元组更优化。
*   `ValueTuple` 通过使用解构和 `_` 关键字，为访问值元组的元素提供了更多的灵活性。但是 `Tuple` 不能提供解构的概念和 `_` 关键字。
*   在 `ValueTuple` 中，像 `Item1` 和 `Item2` 这样的成员是字段。但是在 `Tuple` 中，它们是属性。
*   在 `ValueTuple` 中，字段是可变的。但是在 `Tuple` 中，字段是只读的。

## 创建值元组

与元组不同，值元组提供了一种创建和初始化值元组的简单机制。您可以使用以下 3 种方式创建值元组：

*   **使用构造函数：** 您可以使用 `ValueTuple<T>` 结构提供的构造函数来创建 `ValueTuple`。您可以在其中存储从一到八个带有其类型的元素。

**语法：**

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

**示例：**

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
        ValueTuple<int, int, int, int, int, int, int, ValueTuple<int>> ValTpl3 = new ValueTuple<int,
                                          int, int, int, int, int, int, ValueTuple<int>>(45, 67, 65, 34, 34,
                                                                                    34, 23, new ValueTuple<int>(90));
    }
}
```

*   **使用 Create 方法：** 当我们使用 `ValueTuple<T>` 结构的构造函数来创建值元组时，我们需要提供存储在值元组中的每个元素的类型，这会使您的代码变得繁琐。因此，C# 提供了另一个 `ValueTuple` 结构，它包含用于创建值元组对象的静态方法，而无需提供每个元素的类型。

**语法：**

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

**示例：**

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

*   **使用括号 `()`：** 这是使用括号 `()` 创建值元组的最简单形式，元素放在它们之间。元素以不同的方式存储在 2 种中：
    *   **命名成员：** `ValueTuple` 允许您创建一个元组，其中每个组件都可以有自己的名称。这样您就可以借助它们的名称来访问该组件。它使您的程序更具可读性且易于记忆。您可以将名称分配给左侧或右侧的成员，但不能同时分配给两侧。如果您将名称分配给两侧，则左侧优先于右侧，如下所示：

**例 1：**

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

**例 2：**

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

*   **未命名成员：** 在 `ValueTuple` 中，未命名成员是那些没有名称的成员。它们只是在没有任何名称的情况下创建。如下所示：

**例 1：**

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

**例 2：**

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

## 访问 ValueTuple 成员

这里我们学习如何访问值元组的命名和未命名成员。

*   **访问未命名成员：** 在 `ValueTuple` 中，未命名成员通过使用默认的 `Item` 属性名称（如 `Item1`、`Item2`、`Item3` 等）进行访问。如下例所示：

    **示例：**

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

*   **访问命名成员：** 在 `ValueTuple` 中，命名成员根据其名称使用。无需使用默认的 `Item` 属性访问这些命名成员。如下例所示，`ValueTuple` 包含三个元素，即 `Book_id`、`Author_name` 和 `Book_name`。我们直接根据它们的名称访问这些元素。

    **示例：**

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

    **输出：**

    ```cs
    Book Id: 2340
    Author Name: Arundhati Roy
    Book Name: The God of Small Things
    ```

#### 返回值元组

在 C# 中，您可以从方法中返回一个 `ValueTuple`。如下例所示，`TouristDetails` 方法返回一个包含 3 个元素的 `ValueTuple`:

示例:

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

输出:

```cs
Tourist Details: 
Tourist Id: 384645
Tourist Name: Sophite
Country: USA

```