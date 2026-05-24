# C# |隐式类型化局部变量–var

> 原文:[https://www . geesforgeks . org/c-sharp-隐式类型化-局部变量-var/](https://www.geeksforgeeks.org/c-sharp-implicitly-typed-local-variables-var/)

隐式类型变量是那些没有指定 *[而声明的变量。NET 类型](https://www.geeksforgeeks.org/c-data-types-2/)明确为*。在隐式类型变量中，变量的类型由编译器在编译时从用于初始化变量的值中自动推导出来。C# 3.0 中引入了隐式类型变量的概念。隐式类型化变量不是为了替换普通的变量声明而设计的，它是为了处理一些特殊情况而设计的，比如 LINQ(语言集成查询)。

**问题:** ***为什么叫本地？***

*回答:*不允许在方法中使用 *var* 作为参数值或返回类型，也不允许在类级别定义等。因为隐式类型化变量的 ***范围是局部的*** 。

**例:**

```cs
// C# program to illustrate
// implicitly typed local variable
using System;

public class GFG {

    // declaring and initializing implicitly
    // typed local variable at class level. 
    // It will give compile time error
    var imp = 15;

    // Main method
    static public void Main()
    {

        // trying to print the value of 'imp'
        Console.WriteLine(GFG.imp);
    }
}
```

**编译时错误:**

> prog.cs(10，2):错误 CS0825:上下文关键字 **`var '只能出现在局部变量声明**中

**要点:**

*   Implicit variables are generally declared as follows by using the keyword **var** :

    ```cs
    var ivariable = 10; 
    ```

*   In an implicitly typed variable, it is not allowed to declare multiple *var* in one statement as follows:

    ```cs
     var ivalue = 20, a = 30; // invalid
    ```

*   It is not allowed to use *var* as a field type at the class level.
*   Allow expressions in *var* like

    ```cs
    Var b-=39
    ```

*   In C#, implicitly typed variables like

    ```cs
     var ivalue;   // invalid
    ```

    cannot be declared without any initialization.
*   Null values like

    ```cs
     var value = null;   // invalid
    ```

    are not allowed in implicitly typed variables.
*   The initializer cannot contain any object or collection, but it may contain a new expression that contains an object or collection initializer, such as

    ```cs
    // Not allowed
    var data = { 23, 24, 10};

    // Allowed 
    var data = new int [] {23, 34, 455, 65};

    ```

*   It is not allowed to initialize implicitly typed variables with different types, such as

    ```cs
    // It will give error because
    // the type of the value is different
    // one is of string type and another
    // one is of int type
    var value = "sd" 
    value = new int[]{1, 2, };

    ```

**示例 1:**

```cs
// C# program to illustrate the 
// concept of implicitly typed variable 
using System; 

public class GFG { 

    // Main method 
    static public void Main() 
    { 

        // Declaring and initializing  
        // implicitly typed variables 
        var a = 50; 
        var b = "Welcome! Geeks"; 
        var c = 340.67d; 
        var d = false; 

        // Display the type of the variables 
        Console.WriteLine("Type of 'a' is : {0} ", a.GetType()); 

        Console.WriteLine("Type of 'b' is : {0} ", b.GetType()); 

        Console.WriteLine("Type of 'c' is : {0} ", c.GetType()); 

        Console.WriteLine("Type of 'd' is : {0} ", d.GetType()); 
    } 
} 
```

**输出:**

```cs
Type of 'a' is : System.Int32 
Type of 'b' is : System.String 
Type of 'c' is : System.Double 
Type of 'd' is : System.Boolean

```

**例 2:**

```cs
// C# program to illustrate the
// use of implicitly typed variable
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // implicitly typed variables
        var Base = 13;
        var Height = 20;
        var Area = (Base * Height) / 2;

        // Display result
        Console.WriteLine("Height of triangle is: " + Height 
                      + "\nBase of the triangle is: " + Base);

        Console.Write("Area of the triangle is: {0}", Area);
    }
}
```

**输出:**

```cs
Height of triangle is: 20
Base of the triangle is: 13
Area of the triangle is: 130

```

**注意:**隐式类型的局部变量可以在函数中、foreach 中用作局部变量，在 for 循环中、作为匿名类型、在 LINQ 查询表达式中、在 using 语句中等等。