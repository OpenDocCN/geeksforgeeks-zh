# c# 中方法参数可选的不同方式

> 原文:[https://www . geesforgeks . org/differential-way-to-make-method-parameter-optional-in-c-sharp/](https://www.geeksforgeeks.org/different-ways-to-make-method-parameter-optional-in-c-sharp/)

顾名思义，可选参数不是强制参数，它们是可选的。它有助于排除某些参数的参数。或者我们可以说在可选参数中，没有必要传递方法中的所有参数。这个概念是在 C# 4.0 中引入的。这里我们讨论实现可选参数的不同方法。在 C# 中，有 **4** 种不同类型的可选参数实现，如下所示:

1.  **By using default value:** You can implement optional parameters by using default value. It is the simplest and easiest way to implement the optional parameter. In this way, you just simply define the optional parameters with their default value in the method definition. And always remember the optional parameter is the last parameter in the parameter list of the method. In default value method, when you do not pass the value of the optional parameters, then the optional parameters use their default value and when you pass the parameters for optional parameters, then they will take the passed value not their default value.

    **示例:**这里，我们有两个常规参数，即 *str1* 和 *str2* 以及一个可选参数，即 *str3* 及其默认值。这里，当我们不向可选参数传递任何值时，可选参数使用此默认值，当我们在方法调用中传递可选参数的值时，它将采用传递的值。

    ```cs
    // C# program to illustrate how to create
    // optional parameters using default value
    using System;

    class GFG {

        // Method containing optional parameter
        // Here str3 is a optional parameter
        // with its default value
        static public void my_add(string str1, string str2,
                             string str3 = "GeeksforGeeks")
        {
            Console.WriteLine(str1 + str2 + str3);
        }

        // Main method
        static public void Main()
        {
            my_add("Welcome", "to");
            my_add("This", "is", "C# Tutorial");
        }
    }
    ```

    **Output:**

    ```cs
    WelcometoGeeksforGeeks
    ThisisC# Tutorial

    ```

2.  **By using [Method Overloading](https://www.geeksforgeeks.org/c-sharp-method-overloading/):** You can implement optional parameters concept by using method overloading. In method overloading, we create methods with the same name but with the different parameter list. This method is not the pure way to implement an optional parameter, but you can achieve the optional parameter concept by using this method.

    **例:**这里我们有两个同名的方法，但是这些方法的参数表不同，即第一个 *my_mul* 方法只取一个参数，第二个 *mu_mul* 方法取三个参数。

    ```cs
    // C# program to illustrate how to create
    // optional parameters using method overloading
    using System;

    class GFG {

        // Creating optional parameters
        // Using method overloading
        // Here both methods have the same 
        // name but different parameter list
        static public void my_mul(int a)
        {
            Console.WriteLine(a * a);
        }

        static public void my_mul(int a, 
                           int b, int c)
        {
            Console.WriteLine(a * b * c);
        }

        // Main method
        static public void Main()
        {
            my_mul(4);
            my_mul(5, 6, 100);
        }
    }
    ```

    **Output:**

    ```cs
    16
    3000

    ```