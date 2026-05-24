# c# 中抽象类和接口的区别

> 原文:[https://www . geesforgeks . org/抽象类与 c-sharp 中接口的区别/](https://www.geeksforgeeks.org/difference-between-abstract-class-and-interface-in-c-sharp/)

一个[抽象类](https://www.geeksforgeeks.org/c-abstract-classes/)是用 C# 实现抽象的一种方式。抽象类从来不打算被直接实例化。该类必须包含至少一个抽象方法，在类定义中用关键字或修饰符*抽象*标记。抽象类通常用于定义类层次结构中的基类。

**示例:**

```cs
// C# program to illustrate the
// concept of abstract class
using System;

// abstract class 'G'
public abstract class G {

    // abstract method 'gfg1()'
    public abstract void gfg1();
}

// class 'G' inherit
// in child class 'G1'
public class G1 : G {

    // abstract method 'gfg1()'
    // declare here with
    // 'override' keyword
    public override void gfg1()
    {
        Console.WriteLine("Class name is G1");
    }
}

// class 'G' inherit in
// another child class 'G2'
public class G2 : G {

    // same as the previous class
    public override void gfg1()
    {
        Console.WriteLine("Class name is  G2");
    }
}

// Driver Class
public class main_method {

    // Main Method
    public static void Main()
    {

        // 'obj' is object of class
        // 'G' class '
        // G' cannot
        // be instantiate
        G obj;

        // instantiate class 'G1'
        obj = new G1();

        // call 'gfg1()' of class 'G1'
        obj.gfg1();

        // instantiate class 'G2'
        obj = new G2();

        // call 'gfg1()' of class 'G2'
        obj.gfg1();
    }
}
```

**输出:**

```cs
Class name is G1
Class name is  G2

```

像类一样，[接口](https://www.geeksforgeeks.org/c-interface/)可以有方法、属性、事件和索引器作为其成员。但是接口将只包含成员的声明。接口成员的实现将由隐式或显式实现接口的类给出。

**示例:**

```cs
// C# program to illustrate the
// concept of interface
using System;

// A simple interface
interface interface1 {

    // method having only declaration
    // not definition
    void show();
}

// A class that implements the interface.
class MyClass : interface1 {

    // providing the body part of function
    public void show()
    {
        Console.WriteLine("Welcome to GeeksforGeeks!!!");
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating object
        MyClass obj1 = new MyClass();

        // calling method
        obj1.show();
    }
}
```

**输出:**

```cs
Welcome to GeeksforGeeks!!!
```

#### 抽象类和接口的区别

| 抽象类 | 连接 |
| 它包含声明和定义部分。 | 它只包含一个声明部分。 |
| 多重继承不是通过抽象类实现的。 | 多重继承是通过接口实现的。 |
| 它包含[构造器](https://www.geeksforgeeks.org/c-sharp-constructors/)。 | 它不包含[构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)。 |
| 它可以包含静态成员。 | 它不包含静态成员。 |
| 它可以包含不同类型的访问修饰符，如公共、私有、受保护等。 | 它只包含公共访问修饰符，因为接口中的所有内容都是公共的。 |
| 抽象类的性能很快。 | 接口的性能很慢，因为它需要时间在相应的类中搜索实际的方法。 |
| 它用于实现类的核心标识。 | 它用于实现类的外围能力。 |
| 一个类只能使用一个抽象类。 | 一个类可以使用多个接口。 |
| 如果许多实现是同类的，并且使用共同的行为，那么使用抽象类更好。 | 如果很多实现只共享方法，那么使用接口更好。 |
| 抽象类可以包含方法、字段、常数等。 | 接口只能包含方法。 |
| 它可以完全、部分或不执行。 | 应该全面实施。 |