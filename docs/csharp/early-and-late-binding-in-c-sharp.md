# c# 中的早、晚结合

> 原文:[https://www . geeksforgeeks . org/早-晚-绑定 in-c-sharp/](https://www.geeksforgeeks.org/early-and-late-binding-in-c-sharp/)

当一个对象被分配给特定类型的对象变量时，C# 编译器在[的帮助下执行绑定。NET 框架](https://www.geeksforgeeks.org/introduction-to-net-framework/)。C# 执行两种不同类型的绑定，它们是:

*   **早期绑定或静态绑定***   **Late Binding or Dynamic Binding

    #### 早期绑定

    它在编译时识别并检查[方法](https://www.geeksforgeeks.org/c-methods/)，或[属性](https://www.geeksforgeeks.org/c-properties/)。在这个绑定中，编译器已经知道它是什么类型的对象，以及它持有什么方法或属性，这里的对象是静态对象。早期绑定的性能很快，并且易于编码。它减少了运行时错误的数量。

    **示例:**

    ```cs
    // C# program to illustrate the
    // concept of early binding
    using System;

    class Geeks {

        // data members
        public string name;
        public string subject;

        // public method
        public void details(string name, string subject)
        {
            this.name = name;
            this.subject = subject;
            Console.WriteLine("Myself: " + name);
            Console.WriteLine("My Favorite Subject is: " + subject);
        }
    }

    // Driver class
    class GFG {

        // Main Method
        static void Main(string[] args)
        {

            // creating object of Geeks class
            Geeks g = new Geeks();

            // Calling the method of Geeks class
            g.details("Ankita", "C#");

            // Calling "mymethod()" gives error
            // because this method does not 
            // belong to class Geeks or compiler 
            // does not know mymethod() at compile time
            g.mymethod();
        }
    }
    ```

    **编译时错误:**

    > prog.cs(34，5):错误 CS1061:类型“Geeks”不包含“mymethod”的定义，找不到类型“Geeks”的扩展方法“mymethod”。您是否缺少程序集引用？
    > 程序(5，7):(与先前错误相关的符号位置)

    **解释:**在上面的例子中，我们有一个类叫做*极客*。本课程包含*细节()*方法。这里，编译器已经知道*极客*中存在的属性和方法。但是当我们试图调用 *mymethod()* 时，它会抛出一个错误，因为编译器不知道这个方法。

    #### 后期绑定

    在后期绑定中，编译器不知道它是什么类型的对象，也不知道它持有什么方法或属性，这里的对象是动态对象。对象的类型是根据它在运行时保存在右边的数据来决定的。基本上，后期绑定是通过使用*虚拟*方法来实现的。后期绑定的性能比早期绑定慢，因为它需要在运行时进行查找。

    **示例:**在下面的程序中， *obj* 保存整数类型数据， *obj1* 保存双类型数据。但是编译器不会在编译时解决这些问题。在运行时，这些动态对象被检测并分别转换成`System.Int32`和`System.Double`。这就是为什么运行时解析过程被称为后期绑定。

    ```cs
    // C# program to illustrate the
    // concept of late binding
    using System;

    class GFG {
        static void Main()
        {
            // Dynamic objects
            dynamic obj = 4;
            dynamic obj1 = 5.678;

            // Display the type of objects
            Console.WriteLine("The type of the objects are :");

            // GetType() method is 
            // used to get the type
            Console.WriteLine(obj.GetType());
            Console.WriteLine(obj1.GetType());
        }
    }
    ```

    **输出:**

    ```cs
    The type of the objects are :
    System.Int32
    System.Double

    ```**