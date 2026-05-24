# c# 中的嵌套类

> 原文:[https://www.geeksforgeeks.org/nested-classes-in-c-sharp/](https://www.geeksforgeeks.org/nested-classes-in-c-sharp/)

一个[类](https://www.geeksforgeeks.org/c-class-and-object/)是一个用户定义的蓝图或原型，从它可以创建对象。基本上，一个类将字段和方法(定义动作的成员函数)组合成一个单元。在 C# 中，允许用户在另一个类中定义一个类。这类类被称为嵌套类。该特性使用户能够对仅在一个地方使用的类进行逻辑分组，从而增加了[封装](https://www.geeksforgeeks.org/c-encapsulation/)的使用，并创建了可读性和可维护性更强的代码。

**语法:**

```cs
class Outer_class {

       // Code..

       class Inner_class {

          // Code.. 
       }
}
```

**示例:**

## C#

```cs
// C# program to illustrate the
// concept of nested class
using System;

// Outer class
public class Outer_class {

    // Method of outer class
    public void method1()
    {
        Console.WriteLine("Outer class method");
    }

    // Inner class
    public class Inner_class {

        // Method of inner class
        public void method2()
        {
            Console.WriteLine("Inner class Method");
        }
    }
}

// Driver Class
public class GFG {

    // Main method
    static public void Main()
    {

        // Create the instance of outer class
        Outer_class obj1 = new Outer_class();
        obj1.method1();

        // This statement gives an error because
        // you are not allowed to access inner
        // class methods with outer class objects
        // obj1\. method2();

        // Creating an instance of inner class
        Outer_class.Inner_class obj2 =
                    new Outer_class.Inner_class();

        // Accessing the method of inner class
        obj2.method2();
    }
}
```

**输出:**

```cs
Outer class method
Inner class Method
```

**要点:**

*   嵌套类可以声明为*私有、公共、受保护、内部、受保护内部或私有受保护*。
*   如上例所示，外部类不允许直接访问内部类成员。
*   您可以在外部类中创建内部类的对象。
*   内部类可以访问外部类中声明的静态成员，如下例所示:
    **例:**

## C#

```cs
// C# program to illustrate the
// concept of nested class accessing
// static members of the outer class
using System;

// Outer class
public class Outer_class {

    // Static data member of the outer class
    public static string str = "Geeksforgeeks";

    // Inner class
    public class Inner_class {

        // Static method of Inner class
        public static void method1()
        {

            // Displaying the value of a
            // static member of the outer class
            Console.WriteLine(Outer_class.str);
        }
    }
}

// Driver Class
public class GFG {

    // Main method
    static public void Main()
    {

        // Accessing static method1
        // of the inner class
        Outer_class.Inner_class.method1();
    }
}
```

**输出:**

```cs
Geeksforgeeks
```

*   内部类可以访问外部类中声明的非静态成员，如下例所示:
    **例:**

## C#

```cs
// C# program to illustrate the
// concept of nested class
// accessing non-static member
// of the outer class
using System;

// Outer class
public class Outer_class {

    // Non-static data
    // member of outer class
    public int number = 1000000;

    // Inner class
    public class Inner_class {

        // Static method of Inner class
        public static void method1()
        {
            // Creating the object of the outer class
            Outer_class obj = new Outer_class();

            // Displaying the value of a
            // static member of the outer class
            // with the help of obj
            Console.WriteLine(obj.number);
        }
    }
}

// Driver Class
public class GFG {

    // Main method
    static public void Main()
    {

        // Accessing static method1
        // of inner class
        Outer_class.Inner_class.method1();
    }
}
```

**输出:**

```cs
1000000
```

*   实例内部类可以访问外部类中声明的非静态成员，如下例所示:
    **例:**

## C#

```cs
// C# program to illustrate the
// concept of nested class
// accessing non-static member
// of the outer class
using System;

// Outer class
public class Outer_class {

    // Non-static data
    // member of outer class
    public int number = 2000000;

    // Non-static reference to Inner_class
    // instance.
    public Inner_class Inner { get; set; }

    // Constructor to establish link between
    // instance of Outer_class to its
    // instance of the Inner_class
    public Outer_class() {
        this.Inner = new Inner_class(this);
    }

    // Inner class
    public class Inner_class {

        // private field to hold
        // reference to an instance
        // of the Outer_class
        private Outer_class obj;

        // constructor that establishes
        // a reference to the Outer_class
        // to use within an Inner_cass instance
        public Inner_class(Outer_class outer)
        {
            obj = outer;
        }

        // Method of Inner class
        public void method1()
        {
            // Displaying the value of a
            // member of the outer class
            // with the help of obj
            Console.WriteLine(obj.number);
        }
    }
}

// Driver Class
public class GFG {

    // Main method
    public static void Main()
    {
        // Create instance of Outer_class
        Outer_class Outer = new Outer_class();

        // Accessing static method1
        // of inner class
        Outer.Inner.method1();
    }
}
```

**输出:**

```cs
2000000
```

*   嵌套类的范围由其封闭类的范围限定。
*   默认情况下，嵌套类是私有的。
*   在 C# 中，允许用户将一个类(包括嵌套类)继承到另一个类中。
    **例:**

## C#

```cs
// C# program to illustrate the
// concept inheritance
using System;

// Outer class
public class Outer_class {

    // Method of outer class
    public void method1()
    {
        Console.WriteLine("Outer class method");
    }

    // Inner class
    public class Inner_class {
    }
}

// Derived class
public class Exclass : Outer_class {

    // Method of derived class
    public void func()
    {
        Console.WriteLine("Method of derived class");
    }
}

// Driver Class
public class GFG {

    // Main method
    static public void Main()
    {

        // Creating object of
        // the derived class
        Exclass obj = new Exclass();
        obj.func();
        obj.method1();
    }
}
```

**输出:**

```cs
Method of derived class
Outer class method
```

*   在 C# 中，允许用户从外部类继承嵌套类。