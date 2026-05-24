# C# |泛型–简介

> 原文:[https://www . geesforgeks . org/c-sharp-generics-introduction/](https://www.geeksforgeeks.org/c-sharp-generics-introduction/)

***【通用】*** 是一个允许用户使用占位符定义类和方法的类。泛型被添加到 C# 语言的 2.0 版本中。使用泛型背后的基本思想是允许类型(整数、字符串、…等和用户定义的类型)成为方法、类和接口的参数。集合的一个主要限制是缺乏有效的类型检查。这意味着您可以将任何对象放入集合中，因为 C# 编程语言中的所有类都是从对象基类扩展而来的。这损害了类型安全，并与 C# 作为类型安全语言的基本定义相矛盾。此外，使用集合涉及显式和隐式类型转换形式的大量性能开销，这是从集合中添加或检索对象所必需的。
为了解决类型安全问题， **[。NET](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/)** 框架提供泛型来创建类、结构、接口和方法，这些类、结构、接口和方法都有它们使用的类型的占位符。泛型通常用于为引用和值类型创建类型安全的集合。 **[。NET](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/)** 框架在系统中提供了大量的接口和类。集合。用于实现通用集合的通用命名空间。

#### 

**通用类**

C# 中的泛型是它最强大的特性。它允许您定义类型安全的数据结构。这带来了显著的性能提升和高级代码，因为它有助于重用数据处理算法，而无需复制特定类型的代码。泛型类似于 C++中的模板，但在实现和功能上有所不同。泛型引入了类型参数的概念，因此可以创建方法和类，将数据类型的框架推迟到类或方法被声明并由客户端代码实例化之后。泛型类型比普通系统类型性能更好，因为它们减少了对变量或对象进行装箱、取消装箱和类型转换的需要。
参数类型在泛型类创建中指定。

**要创建泛型类的对象，使用以下语法:**

```cs
BaseType obj = new BaseType <type>()</type> 
```

**示例:**

```cs
// C# program to show working of 
// user defined Generic classes
using System;

// We use < > to specify Parameter type
public class GFG<T> {

    // private data members
    private T data;

    // using properties
    public T value
    {

        // using accessors
        get
        {
            return this.data;
        }
        set
        {
            this.data = value;
        }
    }
}

// Driver class
class Test {

    // Main method
    static void Main(string[] args)
    {

        // instance of string type
        GFG<string> name = new GFG<string>();
        name.value = "GeeksforGeeks";

        // instance of float type
        GFG<float> version = new GFG<float>();
        version.value = 5.0F;

        // display GeeksforGeeks
        Console.WriteLine(name.value); 

        // display 5
        Console.WriteLine(version.value); 
    }
}
```

**输出:**

```cs
GeeksforGeeks
5

```

**解释:**前面的例子定义了一个泛型类， *GFG* ，它使用了一个泛型类型参数‘T’。在 Main()方法中，通过将“T”替换为“string”和“float”数据类型，创建了两个 GFG 实例。这些对象分别用于存储“字符串”和“浮点”值。GFG 类通过在其构造函数中接受所需的类型来确保类型安全。

**带各种参数的泛型方法:**就像一个方法可以取一个参数一样，泛型也可以取各种参数。一个参数可以作为熟悉的类型传递，另一个可以作为泛型类型传递，如下所示:

*   **Example:**

    ```cs
    // C# program to show multiple
    // type parameters in Generics
    using System;

    public class GFG {

        // Generics method
        public void Display<TypeOfValue>(string msg, TypeOfValue value)
        {
            Console.WriteLine("{0}:{1}", msg, value);
        }
    }

    // Driver class
    public class Example {

        // Main Method
        public static int Main()
        {

            // creating object of class GFG
            GFG p = new GFG();

            // calling Generics method
            p.Display<int>("Integer", 122);
            p.Display<char>("Character", 'H');
            p.Display<double>("Decimal", 255.67);
            return 0;
        }
    }
    ```

    **输出:**

    ```cs
    Integer:122
    Character:H
    Decimal:255.67

    ```

**仿制药的特点**

泛型是一种在许多方面改进程序的技术，例如:

*   它有助于代码重用、性能和类型安全。
*   您可以创建自己的泛型类、方法、接口和委托。
*   您可以创建通用集合类。那个。NET 框架类库包含许多新的通用集合类。集合。通用命名空间。
*   您可以在运行时获取有关泛型数据类型中使用的类型的信息。

**仿制药的优势**

*   **可重用性:**您可以在同一代码中为多种目的使用单个泛型类型定义，而无需任何更改。例如，您可以创建一个通用方法来添加两个数字。这个方法可以用来添加两个整数和两个浮点数，而无需对代码进行任何修改。
*   **类型安全性:**泛型数据类型提供了更好的类型安全性，尤其是在集合的情况下。使用泛型时，需要定义要传递给集合的对象类型。这有助于编译器确保只有那些在定义中定义的对象类型才能传递给集合。
*   **性能:**与普通系统类型相比，泛型类型提供了更好的性能，因为它们减少了对变量或对象装箱、取消装箱和类型转换的需要。