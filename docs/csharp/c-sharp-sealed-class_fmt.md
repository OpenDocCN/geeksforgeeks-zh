# C# | 密封类

> 原文: [https://www.geeksforgeeks.org/c-sharp-sealed-class/](https://www.geeksforgeeks.org/c-sharp-sealed-class/)

## 介绍

密封类用于限制用户继承该类。使用 `sealed` 关键字可以封存一个类。`sealed` 关键字告诉编译器类是密封的，因此不能扩展。任何类都不能从密封类派生。

## 密封类的语法

以下是密封类的语法：

```cs
sealed class class_name
{
    // data members
    // methods
    .
    .
    .

}
```

一个方法也可以被封存，在这种情况下，该方法不能被覆盖。然而，一个方法可以被密封在它们被继承的类中。如果你想将一个方法声明为密封的，那么它必须在其基类中声明为 `virtual`。

## 密封类示例

下面的类定义在 C# 中定义了一个密封类：

在下面的代码中，创建一个密封类 `SealedClass`，并从程序中使用它。如果你运行这段代码，那么它会正常工作。

```cs
// C# code to define
// a Sealed Class
using System;

// Sealed class
sealed class SealedClass {

// Calling Function
    public int Add(int a, int b)
    {
        return a + b;
    }
}

class Program {

// Main Method
    static void Main(string[] args)
    {

// Creating an object of Sealed Class
        SealedClass slc = new SealedClass();

// Performing Addition operation
        int total = slc.Add(6, 4);
        Console.WriteLine("Total = " + total.ToString());
    }
}
```

输出：

```cs
Total = 10
```

现在，如果它试图从密封类继承一个类，那么将产生一个错误，声明“它不能从 `SealedClass` 派生”。

```cs
// C# code to show restrictions
// of a Sealed Class
using System;

class Bird {

}

// Creating a sealed class
sealed class Test : Bird {
}

// Inheriting the Sealed Class
class Example : Test {
}

// Driver Class
class Program {

// Main Method
    static void Main()
    {
    }
}
```

错误：

> 错误 CS0509 “Example”: 无法从密封类型 “Test” 派生

## 密封方法示例

考虑下面一个派生类中的密封方法的例子：

```cs
// C# program to
// define Sealed Class
using System;

class Printer {

// Display Function for
    // Dimension printing
    public virtual void show()
    {
        Console.WriteLine("display dimension : 6*6");
    }

// Display Function
    public virtual void print()
    {
        Console.WriteLine("printer printing....\n");
    }
}

// inheriting class
class LaserJet : Printer {

// Sealed Display Function
    // for Dimension printing
    sealed override public void show()
    {
        Console.WriteLine("display dimension : 12*12");
    }

// Function to override
    // Print() function
    override public void print()
    {
        Console.WriteLine("Laserjet printer printing....\n");
    }
}

// Officejet class cannot override show
// function as it is sealed in LaserJet class.
class Officejet : LaserJet {

// can not override show function or else
    // compiler error : 'Officejet.show()' :
    // cannot override inherited member
    // 'LaserJet.show()' because it is sealed.
    override public void print()
    {
        Console.WriteLine("Officejet printer printing....");
    }
}

// Driver Class
class Program {

// Driver Code
    static void Main(string[] args)
    {
        Printer p = new Printer();
        p.show();
        p.print();

Printer ls = new LaserJet();
        ls.show();
        ls.print();

Printer of = new Officejet();
        of.show();
        of.print();
    }
}
```

输出：

```cs
display dimension : 6*6
Printer printing....

display dimension : 12*12
LaserJet printer printing....

display dimension : 12*12
Officejet printer printing....
```

说明：在上面的 C# 代码中，`Printer` 类有尺寸为 6*6 的显示单元，`LaserJet` 类通过将其覆盖为尺寸为 12*12 来实现 `show` 方法。如果任何类将继承 `LaserJet` 类，那么它将具有 12*12 的相同维度，并且不能实现它自己的维度，即它不能具有 15*15、16*16 或任何其他维度。因此，`LaserJet` 调用将密封 `show` 方法，以防止进一步覆盖它。

## 为什么要密封类？

- 密封类用于阻止类被继承。您不能从它派生或扩展任何类。
- 实现密封方法是为了不让其他类推翻它并实现自己的方法。
- 密封类的主要目的是从用户那里收回继承属性，这样他们就不能从密封类中获得类。当您有一个包含静态成员的类时，最好使用密封类。例如 `System.Drawing` 命名空间中的 `Pen` 和 `Brush` 类。`Pen` 类表示标准颜色的笔。这个类只有静态成员。例如，`Pen.Red` 代表红色的笔。类似地，`Brush` 类代表标准画笔。`Brush.Red` 代表红色的画笔。