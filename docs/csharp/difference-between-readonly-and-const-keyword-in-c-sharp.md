# c# 中 readonly 和 const 关键字的区别

> 原文:[https://www . geesforgeks . org/readonly 和-const-关键字 in-c-sharp/](https://www.geeksforgeeks.org/difference-between-readonly-and-const-keyword-in-c-sharp/) 之间的差异

在 C# 中，一个 ***const*** 关键字用来声明常量字段和常量局部。常量字段的值在整个程序中是相同的，换句话说，一旦常量字段被赋值，这个字段的值就不会被改变。在 C# 中，常量字段和局部变量不是变量，常量是数字、字符串、空引用、布尔值。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// use of const keyword
using System;

class GFG {

    // Constant fields
    public const int myvar = 10;
    public const string str = "GeeksforGeeks";

    // Main method
    static public void Main()
    {

        // Display the value of Constant fields
        Console.WriteLine("The value of myvar: {0}", myvar);
        Console.WriteLine("The value of str: {0}", str);
    }
}
```

**输出:**

```cs
The value of myvar: 10
The value of str: GeeksforGeeks
```

在 C# 中，可以使用**等只读关键字来声明只读变量。此 readonly 关键字表明，只有在声明变量或声明变量的同一类的构造函数中，才能分配变量。
**例:**** 

## **c sharp . c sharp . c sharp . c sharp**

```cs
// C# program to illustrate the use
// of the readonly keyword
using System;

class GFG {

    // readonly variables
    public readonly int myvar1;
    public readonly int myvar2;

    // Values of the readonly
    // variables are assigned
    // Using constructor
    public GFG(int b, int c)
    {

        myvar1 = b;
        myvar2 = c;
        Console.WriteLine("Display value of myvar1 {0}, "+
                        "and myvar2 {1}", myvar1, myvar2);
    }

    // Main method
    static public void Main()
    {
        GFG obj1 = new GFG(100, 200);
    }
}
```

****输出:**** 

```cs
Display value of myvar1 100, and myvar2 200
```

#### **只读 Vs 常量关键字**

<figure class="table">

| 只读关键字 | 常量关键字 |
| 在 C# 中，可以使用 readonly 关键字创建只读字段 | 在 C# 中，常量字段是使用 const 关键字创建的。 |
| ReadOnly 是一个运行时常数。 | Const 是编译时常数。 |
| 只读字段的值可以更改。 | 常量字段的值不能更改。 |
| 它不能在方法内部声明。 | 它可以在方法内部声明。 |
| 在只读字段中，我们可以在声明和构造函数部分赋值。 | 在常量字段中，我们只能在声明部分赋值。 |
| 它可以与静态修饰符一起使用。 | 它不能与静态修饰符一起使用。 |

</figure>