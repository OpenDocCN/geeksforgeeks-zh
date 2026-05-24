# C# |命名空间

> 原文:[https://www.geeksforgeeks.org/c-sharp-namespaces/](https://www.geeksforgeeks.org/c-sharp-namespaces/)

命名空间用于组织类。它有助于在更大的 **[中控制方法和类的范围。](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/)网**编程项目。简单来说，你可以说它提供了一种方法来保持一组名称(比如类名)不同于其他组名称。使用名称空间的最大优点是，在一个名称空间中声明的类名不会与在另一个名称空间中声明的类名冲突。它也被称为**命名的具有共同特征的类组**。名称空间的成员可以是**名称空间、[接口](https://www.geeksforgeeks.org/c-interface/)、[结构](https://www.geeksforgeeks.org/c-structures-set-1/)和[委托](https://www.geeksforgeeks.org/c-delegates/)。**

#### 定义命名空间

要在 C# 中定义命名空间，我们将使用**命名空间**关键字，后跟命名空间的名称和包含命名空间主体的花括号，如下所示:

**语法:**

```cs
namespace name_of_namespace {

// Namespace (Nested Namespaces)
// Classes
// Interfaces
// Structures
// Delegates

}

```

**示例:**

```cs
// defining the namespace name1
namespace name1 
{

    // C1 is the class in the namespace name1
    class C1
    {
         // class code
    }
}

```

#### 访问命名空间的成员

命名空间的成员通过使用点(。)运算符。C# 中的类通过其各自的命名空间而完全为人所知。

**语法:**

```cs
[namespace_name].[member_name]

```

**注:**

*   在一个程序中，可以在两个不同的名称空间内创建两个同名的类。
*   在命名空间中，没有两个类可以有相同的名称。
*   在 C# 中，类的全名从其命名空间名称开始，后跟*点(。)*运算符和类名，后者被称为类的完全限定名。

**示例:**

```cs
// C# program to illustrate the 
// use of namespaces

// namespace declaration
namespace first {

    // name_1 namespace members
    // i.e. class
    class Geeks_1 
    {

        // function of class Geeks_1
        public static void display()
        {
            // Here System is the namespace
            // under which Console class is defined
            // You can avoid writing System with 
            // the help of "using" keyword discussed
            // later in this article
            System.Console.WriteLine("Hello Geeks!");

        }
    }

    /* Removing comment will give the error
       because no two classes can have the 
       same name under a single namespace

    class Geeks_1
    {

    }       */

} // ending of first namespace

// Class declaration
class Geeks_2
{

    // Main Method
    public static void Main(String []args)
    {

        // calling the display method of 
        // class Geeks_1 by using two dot
        // operator as one is use to access 
        // the class of first namespace and 
        // another is use to access the 
        // static method of class Geeks_1.
        // Termed as fully qualified name 
        first.Geeks_1.display();        

    } 
}
```

**输出:**

```cs
Hello Geeks!
```

在上例中:

*   在**系统中。Console . WriteLine()**“*系统*”是一个命名空间，在这个命名空间中我们有一个名为“ *Console* 的类，它的方法是“ *WriteLine()* ”。
*   没有必要将 C# 中的每个类都保留在 Namespace 中，但是我们这样做是为了很好地组织我们的代码。
*   这里**。**”是用于分隔类名和命名空间以及函数名和类名的分隔符。

#### using 关键字

每次通过使用函数或类的完全限定名来调用函数或类(或者您可以说是命名空间的成员)实际上是不切实际的。在上例中，*系统。控制台。写线(“你好，极客！”);*和*第一。geeks _ 1 . display()；*是全限定名。所以 C# 提供了一个使用的关键字“**，帮助用户避免一次又一次的写全限定名。用户只需在程序开始时提到名称空间名称，然后就可以轻松避免使用完全限定的名称。**

**语法:**

```cs
using [namespace_name][.][sub-namespace_name];

```

在上面的语法中，*点(。)*用于在程序中包含子名称空间名称。

**示例:**

```cs
// predefined namespace name
using System;

// user-defined namespace name
using name1

// namespace having subnamespace
using System.Collections.Generic;

```

**程序:**

```cs
// C# program to illustrate the 
// use of using keyword

// predefined namespace
using System;

// user defined namespace
using first;

// namespace declaration
namespace first {

    // name_1 namespace members
    // i.e. class
    class Geeks_1 
    {

        // function of class Geeks_1
        public static void display()
        {
            // No need to write fully qualified name
            // as we have used "using System"
            Console.WriteLine("Hello Geeks!");

        }
    }

} // ending of first namespace

// Class declaration
class Geeks_2
{

    // Main Method
    public static void Main(String []args)
    {

        // calling the display method of 
        // class Geeks_1 by using only one 
        // dot operator as display is the 
        // static method of class Geeks_1
        Geeks_1.display();

    } 
}
```

**输出:**

```cs
Hello Geeks!
```

#### 嵌套命名空间

您还可以将一个命名空间定义到另一个命名空间中，该命名空间称为嵌套命名空间。要访问嵌套命名空间的成员，用户必须使用点(。)运算符。

*例如，* *通用*是作为*系统的*集合*命名空间中的嵌套命名空间。集合.通用*

**语法:**

```cs
namespace name_of_namespace_1 
{

   // Member declarations & definitions
   namespace name_of_namespace_2 
   {

        // Member declarations & definitions
        .
        .

   }
}

```

**程序:**

```cs
// C# program to illustrate use of 
// nested namespace
using System;

// You can also use 
// using Main_name.Nest_name;
// to avoid the use of fully 
// qualified name 

// main namespace
namespace Main_name
{            

    // nested namespace
    namespace Nest_name
    {

        // class within nested namespace      
        class Geeks_1
         {

              // Constructor of nested
              // namespace class Geeks_1
              public Geeks_1() { 

                  Console.WriteLine("Nested Namespace Constructor");

              }
        }   
    }                                                    
}

// Driver Class
class Driver 
{

    // Main Method
    public static void Main(string[] args)
    {

        // accessing the Nested Namespace by
        // using fully qualified name
        // "new" is used as Geeks_1() 
        // is the Constructor  
        new Main_name.Nest_name.Geeks_1();

    }    
}
```

**输出:**

```cs
Nested Namespace Constructor

```