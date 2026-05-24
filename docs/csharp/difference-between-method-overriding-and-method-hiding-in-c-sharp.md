# c# 中方法覆盖和方法隐藏的区别

> 原文:[https://www . geeksforgeeks . org/方法覆盖和方法隐藏的区别-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-method-overriding-and-method-hiding-in-c-sharp/)

方法重写是一种允许从派生类中的另一个类(基类)调用函数的技术。在派生类中创建一个与基类中的方法具有相同签名的方法称为 ***方法覆盖*** 。
简单来说，Overriding 是一个允许子类或子类提供某个方法的特定实现的特性，该方法已经由它的一个超类或父类提供。当子类中的方法与其超类中的方法具有相同的名称、相同的参数或签名以及相同的返回类型(或子类型)时，那么子类中的方法被称为覆盖超类中的方法。

**示例:**

```cs
// C# program to illustrate the 
// Method overriding concept
using System;

// Base class
class My_Parent {

    // virtual method
    public virtual void display()
    {
        Console.WriteLine("My new parent class.. !");
    }
}

// Derived class
class My_Child : My_Parent {

    // Here display method is overridden
    public override void display()
    {
        Console.WriteLine("My new child class.. !");
    }
}

class GFG {

    // Main Method
    public static void Main()
    {

        My_Parent obj;

        // Creating object of the base class
        obj = new My_Parent();

        // Invoking method of the base class
        obj.display();

        // Creating object of the derived class
        obj = new My_Child();

        // Invoking method of derived class
        obj.display();
    }
}
```

**输出:**

```cs
My new parent class.. !
My new child class.. !

```

在 ***方法隐藏*** 中，可以使用*新*关键字从派生类中隐藏基类方法的实现。或者换句话说，在方法隐藏中，可以使用 new 关键字在派生类中重新定义基类的方法。

**示例:**

```cs
// C# program to illustrate the
// concept of method hiding
using System;

// Base Class
public class My_Parent {

    public void show()
    {
        Console.WriteLine("This is my parent class.");
    }
}

// Derived Class
public class My_Child : My_Parent {

    // Hide the method of base class
    // Using new keyword
    public new void show() {

        Console.WriteLine("This is my child class.");
    }
}

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating the object of 
        // the derived class
        My_Child obj = new My_Child();

        // Access the method of derived class
        obj.show();
    }
}
```

**输出:**

```cs
This is my child class.
```

#### 方法覆盖与方法隐藏

| 方法重写 | 方法隐藏 |
| 在方法重写中，需要使用 virtual 关键字将父类的方法定义为虚拟方法，使用 override 关键字将子类的方法定义为重写方法。 | 在方法隐藏中，您只需在父类中创建一个方法，在子类中，您需要使用 new 关键字定义该方法。 |
| 它只是重新定义了方法的实现。 | 在方法隐藏中，可以完全重新定义方法。 |
| 这里覆盖的是一个对象类型。 | 这里隐藏是一种引用类型。 |
| 如果不使用 override 关键字，则编译器不会重写该方法。而不是重写编译器将隐藏该方法。 | 如果不使用 new 关键字，编译器将自动隐藏基类的方法。 |
| 在方法重写中，当基类引用指向派生类对象的变量时，它将调用派生类中被重写的方法。 | 在方法隐藏中，当基类引用变量指向派生类的对象时，它将调用基类中的隐藏方法。 |