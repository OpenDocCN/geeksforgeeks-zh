# c# 中的部分方法

> 原文:[https://www.geeksforgeeks.org/partial-methods-in-c-sharp/](https://www.geeksforgeeks.org/partial-methods-in-c-sharp/)

C# 包含一种特殊的方法称为分部方法，它包含一个分部类中的声明部分和另一个分部类中的定义部分，或者可能同时包含同一个分部类中的声明和定义。
基本上，分部方法存在于分部类中，或者结构中。分部方法可能包含也可能不包含实现如果分部方法在任何部分都不包含实现，那么编译器将不会在最终类或驱动程序类中创建该方法。借助 *partial* 关键字声明一个 partial 方法，如下所示。

**语法:**

```cs
partial void method_name
{
    // Code
}

```

**要点:**

*   分部方法的声明必须以分部修饰符开始。
*   分部方法可能包含 ref。
*   部分方法不包含[输出参数](https://www.geeksforgeeks.org/out-parameter-with-examples-in-c/)。
*   它是隐式私有方法。
*   它可以是静态方法。
*   分部方法是通用的。
*   它只能有 void 返回类型。
*   分部方法只在分部类或分部结构中创建。

**示例:**我们有一个类名为*圆*。 *Circle* 类的功能被分成两个不同的文件，分别命名为`circle1.cs`和`circle2.cs`。这些`circle1.cs`和`circle2.cs`文件包含*圆*类和分部方法的分部类，即*区域*。`circle1.cs`文件包含*局部区域()方法*的声明，`circle2.cs`文件包含*区域*方法的实现，如下所示:

**大约 1.cs**

```cs
public partial class Circle {

    // This file only contains
    // declaration of partial method
    partial void area(int p);

    public void Display()
    {
        Console.WriteLine("Example of partial method");
    }
}
```

**大约 2.cs**

```cs
public partial class Circle {

    public void newarea(int a)
    {
        area(int a);
    }

    // This is the definition of
    // partial method
    partial void area(int r)
    {
        int A = 3.14 * r * r;
        Console.WriteLine("Area is : {0}", A);
    }
}
```

当我们执行上述代码时，编译器将`circle1.cs`和`circle2.cs`合并成一个文件，即*圆*，如下图。

**圆**

```cs
public class Circle {

    public void Display()
    {
        Console.WriteLine("Example of partial method");
    }

    public void newarea(int a)
    {
        area(int a);
    }

    private void area(int r)
    {
        int A = 3.14 * r * r;
        Console.WriteLine("Area is : {0}", A);
    }
}
```