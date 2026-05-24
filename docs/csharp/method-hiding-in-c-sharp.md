# 隐藏在 C# 中的方法

> 原文:[https://www.geeksforgeeks.org/method-hiding-in-c-sharp/](https://www.geeksforgeeks.org/method-hiding-in-c-sharp/)

正如我们已经知道的多态性和 C# 中的[方法覆盖](https://www.geeksforgeeks.org/c-method-overriding/)。C# 还提供了一个从派生类中隐藏基类方法的概念，这个概念被称为方法隐藏。也被称为**法影**。在方法隐藏中，您可以使用 *new* 关键字从派生类中隐藏基类方法的实现。或者换句话说，在方法隐藏中，可以使用 *new* 关键字在派生类中重新定义基类的方法。

**示例:**

```cs
// C# program to illustrate the
// concept of method hiding
using System;

// Base Class
public class My_Family {

    public void member()
    {
        Console.WriteLine("Total number of family members: 3");
    }
}

// Derived Class
public class My_Member : My_Family {

    // Reimplement the method of the base class
    // Using new keyword
    // It hides the method of the base class
    public new void member() 
    {
        Console.WriteLine("Name: Rakesh, Age: 40 \nName: Somya, "+
                               "Age: 39 \nName: Rohan, Age: 20 ");
    }
}

// Driver Class
class GFG {

    // Main method
    static public void Main()
    {

        // Creating the object of the derived class
        My_Member obj = new My_Member();

        // Access the method of derived class
        obj.member();
    }
}
```

**输出:**

```cs
Name: Rakesh, Age: 40 
Name: Somya, Age: 39 
Name: Rohan, Age: 20 

```

**说明:**上例中， *My_Family* 为基类， *My_Member* 为派生类。在这两个类中，我们有相同名称的方法，即*成员()*方法。但是在派生类中，*成员()*方法是用新关键字声明的。调用此方法时，它会打印家庭成员的姓名和年龄，而不是家庭成员的总数。这意味着当我们借助派生类对象调用*成员()*方法时，由于新关键字的存在，它隐藏了基类中存在的同名方法。

现在我们将看到如果我们不使用 *new* 关键字来隐藏派生类中基类的方法会发生什么。如下例所示，当我们不使用 new 关键字时，编译器会给出运行代码而不会给出错误，但它会给出警告，如果你想隐藏一个方法，那么就使用 new 关键字。

**示例:**

```cs
// C# program to illustrate the
// concept of method hiding
// without using the new keyword
using System;

// Base Class
public class My_Family {

    public void member()
    {
        Console.WriteLine("Total number of family members: 3");
    }
}

// Derived Class
public class My_Member : My_Family {

    public void member()
    {
        Console.WriteLine("Name: Rakesh, Age: 40 \nName: Somya, "+
                               "Age: 39 \nName: Rohan, Age: 20 ");
    }
}

class GFG {

    // Main method
    static public void Main()
    {

        // Creating the object of the derived class
        My_Member obj = new My_Member();

        // Access the method of derived class
        obj.member();
    }
}
```

**警告:**

> prog.cs(18，14):警告 CS0108: `My_Member.member()'隐藏继承的成员` My_Family.member()'。如果打算隐藏
> 程序(9，14):(与先前警告相关的符号的位置)，则使用新的关键字

**输出:**

```cs
Name: Rakesh, Age: 40 
Name: Somya, Age: 39 
Name: Rohan, Age: 20 

```

#### 如何调用隐藏方法？

在方法隐藏中，也可以使用**三种不同的方式调用派生类中基类的隐藏方法，方式为:**

*   ***By using the base keyword*** you can call the hidden method of the base class in your derived class shown in the below example:

    **示例:**

    ```cs
    // C# program to illustrate how
    // to access hidden method
    using System;

    // Base Class
    public class My_Family {
        public void member()
        {
            Console.WriteLine("Total number of family members: 3");
        }
    }

    // Derived Class
    public class My_Member : My_Family {

        public new void member() 
        {

            // Calling the hidden method of the
            // base class in a derived class
            // Using base keyword
            base.member();
            Console.WriteLine("Name: Rakesh, Age: 40 \nName: Somya,"+
                                  " Age: 39 \nName: Rohan, Age: 20");
        }
    }

    class GFG {

        // Main method
        static public void Main()
        {

            // Creating the object of the derived class
            My_Member obj = new My_Member();

            // Access the method of derived class
            obj.member();
        }
    }
    ```

    **输出:**

    ```cs
    Total number of family members: 3
    Name: Rakesh, Age: 40 
    Name: Somya, Age: 39 
    Name: Rohan, Age: 20

    ```

*   ***By casting the derived class type to base class type*** you can invoke the hidden method. As shown in the below example. We know that in inheritance the derived class has all the capabilities of the base class so we can easily cast the object of a derived class into base class type.

    **示例:**

    ```cs
    // C# program to illustrate how
    // to access hidden method
    using System;

    // Base Class
    public class My_Family {

        public void member()
        {
            Console.WriteLine("Total number of family members: 2");
        }
    }

    // Derived Class
    public class My_Member : My_Family {

        public new void member() {

            Console.WriteLine("Name: Rakesh, Age: 40 "+
                             "\nName: Somya, Age: 39");
        }
    }

    class GFG {

        // Main method
        static public void Main()
        {

            // Creating the object of the derived class
            My_Member obj = new My_Member();

            // Invoking the hidden method
            // By type casting
            ((My_Family)obj).member();
        }
    }
    ```

    **输出:**

    ```cs
    Total number of family members: 2

    ```

*   Instead of using derived class reference variable we use the parent class reference variable for calling the hidden method. It is similar to the above way of calling a hidden method. Here we also type case the object of the derived class in a different syntax.

    **注意:**如果试图使用以下语法调用隐藏方法，

    ```cs
    My_Member obj = new My_Family();
    ```

    这里编译器会给出一个错误，因为 *My_Family* 类的对象不能履行 *My_Member* 类的职责。

    **示例:**

    ```cs
    // C# program to illustrate how
    // to access hidden method
    using System;

    // Base Class
    public class My_Family {

        public void member()
        {
            Console.WriteLine("Total number of family members: 2");
        }
    }

    // Derived Class
    public class My_Member : My_Family {

        public new void member() {

            Console.WriteLine("Name: Rakesh, Age: 40 "+
                             "\nName: Somya, Age: 39");
        }
    }

    class GFG {

        // Main method
        static public void Main()
        {

            // Invoking the hidden method
            My_Family obj = new My_Member();
            obj.member();
        }
    }
    ```

    **输出:**

    ```cs
    Total number of family members: 2

    ```