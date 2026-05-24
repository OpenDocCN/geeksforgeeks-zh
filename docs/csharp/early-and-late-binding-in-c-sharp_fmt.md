# C# 中的早、晚结合

> 原文：[https://www.geeksforgeeks.org/early-and-late-binding-in-c-sharp/](https://www.geeksforgeeks.org/early-and-late-binding-in-c-sharp/)

当一个对象被分配给特定类型的对象变量时，C# 编译器在 [.NET 框架](https://www.geeksforgeeks.org/introduction-to-net-framework/)的帮助下执行绑定。C# 执行两种不同类型的绑定，它们是：

*   **早期绑定或静态绑定**
*   **后期绑定或动态绑定**

## 早期绑定

它在编译时识别并检查[方法](https://www.geeksforgeeks.org/c-methods/)或[属性](https://www.geeksforgeeks.org/c-properties/)。在这个绑定中，编译器已经知道它是什么类型的对象，以及它持有什么方法或属性，这里的对象是静态对象。早期绑定的性能很快，并且易于编码。它减少了运行时错误的数量。

**示例：**

```cs
// C# program to illustrate the
// concept of early binding
using System;

class Geeks {

    // data members
    public string name;
    public string subject;

    // public method
    public void details(string name, string subject)
    {
        this.name = name;
        this.subject = subject;
        Console.WriteLine("Myself: " + name);
        Console.WriteLine("My Favorite Subject is: " + subject);
    }
}

// Driver class
class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // creating object of Geeks class
        Geeks g = new Geeks();

        // Calling the method of Geeks class
        g.details("Ankita", "C#");

        // Calling "mymethod()" gives error
        // because this method does not
        // belong to class Geeks or compiler
        // does not know mymethod() at compile time
        g.mymethod();
    }
}
```

**编译时错误：**

> prog.cs(34,5): error CS1061: Type `Geeks` does not contain a definition for `mymethod` and no accessible extension method `mymethod` of type `Geeks` could be found (are you missing a using directive or an assembly reference?)
> prog.cs(5,7): (Location of the symbol related to previous error)

**解释：** 在上面的例子中，我们有一个叫做 `Geeks` 的类。这个类包含 `details()` 方法。这里，编译器已经知道 `Geeks` 中存在的属性和方法。但是当我们试图调用 `mymethod()` 时，它会抛出一个错误，因为编译器不知道这个方法。

## 后期绑定

在后期绑定中，编译器不知道它是什么类型的对象，也不知道它持有什么方法或属性，这里的对象是动态对象。对象的类型是根据它在运行时保存在右边的数据来决定的。基本上，后期绑定是通过使用 `virtual` 方法来实现的。后期绑定的性能比早期绑定慢，因为它需要在运行时进行查找。

**示例：** 在下面的程序中，`obj` 保存整数类型数据，`obj1` 保存双精度类型数据。但是编译器不会在编译时解决这些问题。在运行时，这些动态对象被检测并分别转换成 `System.Int32` 和 `System.Double`。这就是为什么运行时解析过程被称为后期绑定。

```cs
// C# program to illustrate the
// concept of late binding
using System;

class GFG {
    static void Main()
    {
        // Dynamic objects
        dynamic obj = 4;
        dynamic obj1 = 5.678;

        // Display the type of objects
        Console.WriteLine("The type of the objects are :");

        // GetType() method is
        // used to get the type
        Console.WriteLine(obj.GetType());
        Console.WriteLine(obj1.GetType());
    }
}
```

**输出：**

```cs
The type of the objects are :
System.Int32
System.Double
```