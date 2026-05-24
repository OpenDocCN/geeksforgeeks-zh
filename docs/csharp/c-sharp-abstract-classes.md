# C# |抽象类

> 原文:[https://www.geeksforgeeks.org/c-sharp-abstract-classes/](https://www.geeksforgeeks.org/c-sharp-abstract-classes/)

[**c# 中的抽象**](https://www.geeksforgeeks.org/c-abstraction/) 就是隐藏内部细节，只展示功能性的过程。**抽象修饰语**表示未完全实现。关键字**抽象**用于类或方法之前，将类或方法声明为抽象。此外，**抽象**修饰符可以与 [**索引器**](https://www.geeksforgeeks.org/c-indexers/) 、事件和 [**属性**](https://www.geeksforgeeks.org/c-properties/) 一起使用。

**示例:**

```cs
public abstract void geek();
// this indicates the method 'geek()' is abstract

abstract class gfg
// this indicates the class 'gfg' is abstract
```

**抽象方法:**声明为抽象的方法，没有“体”，只在抽象类内部声明。必须使用 override 关键字在所有非抽象类中实现抽象方法。重写后，抽象方法在非抽象类中。我们可以在另一个类中派生这个类，同样，我们可以用它重写同一个抽象方法。

**语法:**

```cs
public abstract void geek();
// the method 'geek()' is abstract
```

**抽象类:**这是 C# 中实现抽象的方式。抽象类从来不打算被直接实例化。该类必须至少包含一个*抽象方法*，在类定义中用关键字或修饰符*抽象*标记。抽象类通常用于定义*类层次结构*中的基类。或者换句话说，抽象类是我们不能实例化的不完整类或者特殊类。抽象类的目的是为派生类提供蓝图，并设置派生类继承抽象类时必须实现的一些规则。我们可以使用抽象类作为基类，所有的派生类都必须实现抽象定义。

**语法:**

```cs
abstract class gfg{}
// class 'gfg' is abstract
```

**要点:**

*   一般我们在*继承*的时候使用抽象类。
*   用户必须在子类中声明为抽象的方法之前使用*覆盖*关键字，抽象类用于在子类中继承。
*   抽象类不能被结构继承。
*   它可以包含构造函数或析构函数。
*   它可以用非抽象方法实现函数。
*   它不能支持多重继承。
*   不可能是静止的。

**示例 1:** 显示抽象类工作的程序

## C#

```cs
// C# program to show the
// working of abstract class
using System;

// abstract class 'GeeksForGeeks'
public abstract class GeeksForGeeks {

    // abstract method 'gfg()'
    public abstract void gfg();

}

// class 'GeeksForGeeks' inherit
// in child class 'Geek1'
public class Geek1 : GeeksForGeeks
{

    // abstract method 'gfg()'
    // declare here with
    // 'override' keyword
    public override void gfg()
    {
        Console.WriteLine("class Geek1");
    }
}

// class 'GeeksForGeeks' inherit in
// another child class 'Geek2'
public class Geek2 : GeeksForGeeks
{

    // same as the previous class
    public override void gfg()
    {
        Console.WriteLine("class Geek2");
    }
}

// Driver Class
public class main_method {

    // Main Method
    public static void Main()
    {

        // 'g' is object of class
        // 'GeeksForGeeks' class '
        // GeeksForGeeks' cannot
        // be instantiate
        GeeksForGeeks g;

        // instantiate class 'Geek1'
        g = new Geek1();

        // call 'gfg()' of class 'Geek1'
        g.gfg();

        // instantiate class 'Geek2' 
        g = new Geek2();

        // call 'gfg()' of class 'Geek2'
        g.gfg();

    }
}
```

**Output:** 

```cs
class Geek1
class Geek2
```

**例 2:** 用抽象类和抽象方法计算正方形面积的程序

## C#

```cs
// C# program to calculate the area
// of a Square using abstract class
// and abstract method
using System;

// declare class 'AreaClass'
// as abstract
abstract class AreaClass
{
    // declare method
    // 'Area' as abstract
    abstract public int Area();
}

// class 'AreaClass' inherit
// in child class 'Square'
class Square : AreaClass
{
    int side = 0;

    // constructor
    public Square(int n)
    {
        side = n;
    }

    // the abstract method
    // 'Area' is overridden here
    public override int Area()
    {
        return side * side;
    }
}

class gfg {

    // Main Method
    public static void Main()
    {
        Square s = new Square(6);
        Console.WriteLine("Area  = " + s.Area());
    }
}
```

**Output:** 

```cs
Area  = 36
```

**下面是一些关于 C# 中抽象类的重要观察**
**1)** 一个抽象类并不意味着它只包含*抽象方法*。一个**抽象类**也可以包含*非抽象方法也*。

**语法:**

```cs
abstract class gfg
{
    public void geek()
    {
        Console.WriteLine("'geek()' is non-abstract method");
    }
}
```

**示例:**

## C#

```cs
// C# program to show the working of
// the non-abstract method in the
// abstract class
using System;

abstract class AbstractClass {

    // Non abstract method
    public int AddTwoNumbers(int Num1, int Num2)
    {
        return Num1 + Num2;
    }

    // An abstract method which
    // overridden in the derived class
    public abstract int MultiplyTwoNumbers(int Num1, int Num2);

}

// Child Class of AbstractClass
class Derived : AbstractClass {

    // implementing the abstract
    // method 'MultiplyTwoNumbers'
    // using override keyword,
    public override int MultiplyTwoNumbers(int Num1, int Num2)
    {
        return Num1 * Num2;
    }
}

// Driver Class
class geek {

    // Main Method
    public static void Main()
    {

        // Instance of the derived class
        Derived d = new Derived();

        Console.WriteLine("Addition : {0}\nMultiplication :{1}",
                                          d.AddTwoNumbers(4, 6),
                                    d.MultiplyTwoNumbers(6, 4));
    }
}
```

**Output:** 

```cs
Addition : 10
Multiplication :24
```

**2)** 抽象类也可以和**一起工作获取**和**设置** [**访问器**](https://www.geeksforgeeks.org/c-properties/) 。

**示例:**

## C#

```cs
// C# program to show the working
// of abstract class with the
// get and set accessors
using System;

abstract class absClass {

    protected int myNumber;

    public abstract int numbers
    {
        get;
        set;
    }
}

class absDerived : absClass {

    // Implementing abstract properties
    public override int numbers
    {
        get
        {
            return myNumber;
        }
        set
        {
            myNumber = value;
        }
    }
}

// Driver Class
class geek {

    // Main Method
    public static void Main()
    {
        absDerived d = new absDerived();
        d.numbers = 5;
        Console.WriteLine(d.numbers);
    }
}
```

**Output:** 

```cs
5
```