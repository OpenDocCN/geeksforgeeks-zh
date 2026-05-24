# C# |抽象

> 原文:[https://www.geeksforgeeks.org/c-sharp-abstraction/](https://www.geeksforgeeks.org/c-sharp-abstraction/)

数据抽象是一种属性，通过它，只有基本的细节才能展示给用户。琐碎的或非必需品不会展示给用户。
数据抽象也可以定义为只识别对象所需特征而忽略无关细节的过程。对象的属性和行为使其区别于其他类似类型的对象，也有助于对对象进行分类/分组。

**例:**考虑一个现实生活中从 ATM 机取钱的场景。用户只知道在 ATM 机中首先输入 ATM 卡，然后输入 ATM 卡的 pin 码，然后输入他/她想要提取的金额，最后得到他们的钱。用户不知道自动取款机的内部机制或取款的实施等。用户只是简单的知道如何操作 ATM 机，这叫抽象。

在 C# 中，抽象是借助**抽象类**实现的。

**抽象类**

*   借助**抽象**关键字声明一个抽象类。
*   在 C# 中，你是**而不是**被允许创建抽象类的对象。或者换句话说，您不能将抽象类直接与新运算符一起使用。
*   包含抽象关键字及其某些方法(并非所有抽象方法)的类称为**抽象基类**。
*   包含抽象关键字及其所有方法的类称为纯抽象基类。
*   不允许在抽象类之外声明抽象方法。
*   不允许将抽象类声明为 [**密封类**](https://www.geeksforgeeks.org/c-sealed-class/) 。

### 通过示例使用抽象类和抽象方法

在某些情况下，我们希望定义一个超类来声明给定抽象的结构，而不提供每个方法的完整实现。也就是说，有时我们想创建一个超类，它只定义一个通用的表单，它的所有子类都将共享这个表单，让每个子类来填写细节。

考虑一个经典的“形状”例子，也许用于计算机辅助设计系统或游戏模拟。基本类型是“形状”，每个形状都有颜色、大小等。由此衍生(继承)出特定类型的形状——圆形、正方形、三角形等等——每一种形状都可能具有额外的特征和行为。例如，某些形状可以翻转。有些行为可能会有所不同，例如当您想要计算正方形的面积时。

**示例:**

## C#

```cs
// C# program to calculate the area
// of a square using the concept of
// data abstraction
using System;

namespace Demoabstraction {

// abstract class
abstract class Shape {

    // abstract method
    public abstract int area();
}

// square class inheriting
// the Shape class
class Square : Shape {

    // private data member
    private int side;

    // method of  square class
    public Square(int x = 0)
    {
        side = x;
    }

    // overriding of the abstract method of Shape
    // class using the override keyword
    public override int area()
    {
        Console.Write("Area of Square: ");
        return (side * side);
    }
}

// Driver Class
class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // creating reference of Shape class
        // which refer to Square class instance
        Shape sh = new Square(4);

        // calling the method
        double result = sh.area();

        Console.Write("{0}", result);

    }
}
}
```

**Output:** 

```cs
Area of Square: 16
```

### 封装与数据抽象

*   [](https://www.geeksforgeeks.org/c-encapsulation/)**封装是数据隐藏(信息隐藏)，抽象是细节隐藏(实现隐藏)。**
*   **虽然封装将数据和对数据起作用的方法组合在一起，但是数据抽象处理向用户公开和隐藏实现的细节。**

### **抽象的优势**

*   **它降低了观察事物的复杂性。**
*   **避免代码重复并提高可重用性。**
*   **有助于提高应用程序或程序的安全性，因为只有重要的细节才提供给用户。**