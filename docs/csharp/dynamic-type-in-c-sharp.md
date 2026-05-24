# c# 中的动态类型

> 原文:[https://www.geeksforgeeks.org/dynamic-type-in-c-sharp/](https://www.geeksforgeeks.org/dynamic-type-in-c-sharp/)

在 C# 4.0 中，引入了一种新的类型，称为动态类型。它用于避免编译时类型检查。编译器不会在编译时检查动态类型变量的类型，而是在运行时获取类型。动态类型变量是使用动态关键字创建的。

**示例:**

```cs
dynamic value = 123;
```

**要点:**

*   在大多数情况下，动态类型的行为类似于对象类型。
*   You can get the actual type of the dynamic variable at runtime by using *GetType()* method. The dynamic type changes its type at the run time based on the value present on the right-hand side. As shown in the below example.

    **示例:**

    ```cs
    // C# program to illustrate how to get the
    // actual type of the dynamic type variable
    using System;

    class GFG {

        // Main Method
        static public void Main()
        {

            // Dynamic variables
            dynamic value1 = "GeeksforGeeks";
            dynamic value2 = 123234;
            dynamic value3 = 2132.55;
            dynamic value4 = false;

            // Get the actual type of 
            // dynamic variables
            // Using GetType() method
            Console.WriteLine("Get the actual type of value1: {0}",
                                      value1.GetType().ToString());

            Console.WriteLine("Get the actual type of value2: {0}",
                                      value2.GetType().ToString());

            Console.WriteLine("Get the actual type of value3: {0}",
                                      value3.GetType().ToString());

            Console.WriteLine("Get the actual type of value4: {0}", 
                                      value4.GetType().ToString());
        }
    }
    ```

    **输出:**

    ```cs
    Get the actual type of value1: System.String
    Get the actual type of value2: System.Int32
    Get the actual type of value3: System.Double
    Get the actual type of value4: System.Boolean

    ```

*   当您将类对象分配给动态类型时，编译器不会检查包含自定义类对象的动态类型的正确方法和属性名称。
*   You can also pass a dynamic type parameter in the method so that the method can accept any type of parameter at run time. As shown in the below example.

    **示例:**

    ```cs
    // C# program to illustrate how to pass
    // dynamic type parameters in the method
    using System;

    class GFG {

        // Method which contains dynamic parameters
        public static void addstr(dynamic s1, dynamic s2)
        {
            Console.WriteLine(s1 + s2);
        }

        // Main method
        static public void Main()
        {

            // Calling addstr method
            addstr("G", "G");
            addstr("Geeks", "forGeeks");
            addstr("Cat", "Dog");
            addstr("Hello", 1232);
            addstr(12, 30);
        }
    }
    ```

    **输出:**

    ```cs
    GG
    GeeksforGeeks
    CatDog
    Hello1232
    42

    ```

*   如果方法和属性不兼容，编译器将在运行时引发异常。
*   它不支持 visual studio 中的*智能感知*。
*   如果没有对动态类型进行类型检查，编译器在编译时不会在动态类型上引发错误。