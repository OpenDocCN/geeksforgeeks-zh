# C# |方法重载

> 原文:[https://www.geeksforgeeks.org/c-sharp-method-overloading/](https://www.geeksforgeeks.org/c-sharp-method-overloading/)

***方法重载*** 是实现多态性的常用方式。它是以多种形式重新定义函数的能力。用户可以通过在一个共享相同名称的类中定义两个或多个函数来实现函数重载。C# 可以用**不同的方法签名**来区分方法。即这些方法可以具有相同的名称，但是在同一类中具有不同的参数列表(即参数的数量、参数的顺序和参数的数据类型)。

*   重载方法根据作为参数传递给方法的参数的数量和类型进行区分。
*   不能用相同的名称、顺序和参数类型定义多个方法。这将是编译器错误。
*   编译器在区分重载方法时不考虑返回类型。但是不能用相同的签名和不同的返回类型声明两个方法。它将引发编译时错误。如果两个方法具有相同的参数类型，但是返回类型不同，那么这是不可能的。

**为什么我们需要方法重载？**

如果我们需要以不同的方式进行同样的操作，即针对不同的输入。在下面描述的例子中，我们对不同的输入进行加法运算。很难为一个动作找到许多不同的有意义的名字。

**做重载方法的不同方式-**
方法重载可以通过改变:

1.  两种方法中的参数数量。
2.  方法参数的数据类型。
3.  方法参数的顺序。

**通过改变参数数量**

## C#

```cs
// C# program to demonstrate the function
// overloading by changing the Number
// of parameters
using System;
class GFG {

    // adding two integer values.
    public int Add(int a, int b)
    {
        int sum = a + b;
        return sum;
    }

    // adding three integer values.
    public int Add(int a, int b, int c)
    {
        int sum = a + b + c;
        return sum;
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating Object
        GFG ob = new GFG();

        int sum1 = ob.Add(1, 2);
        Console.WriteLine("sum of the two "
                          + "integer value : " + sum1);

        int sum2 = ob.Add(1, 2, 3);
        Console.WriteLine("sum of the three "
                          + "integer value : " + sum2);
    }
}
```

**Output:** 

```cs
sum of the two integer value : 3
sum of the three integer value : 6
```

**通过改变参数的数据类型**

## C#

```cs
// C# program to demonstrate the function
// overloading by changing the Data types
//  of the parameters
using System;
class GFG {

    // adding three integer values.
    public int Add(int a, int b, int c)
    {
        int sum = a + b + c;
        return sum;
    }

    // adding three double values.
    public double Add(double a,
                      double b, double c)
    {
        double sum = a + b + c;
        return sum;
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating Object
        GFG ob = new GFG();

        int sum2 = ob.Add(1, 2, 3);
        Console.WriteLine("sum of the three "
                          + "integer value : " + sum2);
        double sum3 = ob.Add(1.0, 2.0, 3.0);
        Console.WriteLine("sum of the three "
                          + "double value : " + sum3);
    }
}
```

**Output:** 

```cs
sum of the three integer value : 6
sum of the three double value : 6
```

**通过改变参数的顺序**

## C#

```cs
// C# program to demonstrate the function
// overloading by changing the
// Order of the parameters
using System;
class GFG {

    // Method
    public void Identity(String name, int id)
    {

        Console.WriteLine("Name1 : " + name + ", "
                        + "Id1 : " + id);
    }

    // Method
    public void Identity(int id, String name)
    {

        Console.WriteLine("Name2 : " + name + ", "
                        + "Id2 : " + id);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating Object
        GFG obj = new GFG();

        obj.Identity("Akku", 1);
        obj.Identity(2, "Abby");
    }
}
```

**输出:**

```cs
Name1 : Akku, Id1 : 1
Name2 : Abby, Id2 : 2
```

**方法签名相同，返回类型不同会怎样？**
编译器会给出错误，因为仅返回值不足以让编译器找出它必须调用哪个函数。只有当两个方法具有不同的参数类型时(因此，它们具有不同的签名)，方法重载才是可能的。

**示例:**

## C#

```cs
// C# program to show error when method signature
// is the same and the return type is different.
using System;
class GFG {

    // adding two integer value.
    public int Add(int a, int b)
    {

        int sum = a + b;
        return sum;
    }

    // adding three integer value.
    public double Add(int a, int b)
    {
        double sum = a + b + 0.0;
        return sum;
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating Object
        GFG ob = new GFG();

        int sum1 = ob.Add(1, 2);
        Console.WriteLine("sum of the two "
                          + "integer value :" + sum1);

        int sum2 = ob.Add(1, 2);
        Console.WriteLine("sum of the three "
                          + "integer value :" + sum2);
    }
}
```

**编译时错误:**

> prog.cs(15，19):错误 CS0111:已经定义了成员` GFG.Add(int，int)'。重命名该成员或使用不同的参数类型
> 程序(7，16):(与先前错误相关的符号位置)