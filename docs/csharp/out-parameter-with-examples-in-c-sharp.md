# 用 C# 中的例子输出参数

> 原文:[https://www . geeksforgeeks . org/out-参数-带示例-in-c-sharp/](https://www.geeksforgeeks.org/out-parameter-with-examples-in-c-sharp/)

**是 C# 中的一个关键字，用于将参数作为引用类型传递给方法。它通常在一个方法返回多个值时使用。**

****要点:****

***   Similar ref keyword. But the main *difference between ref and out keywords is that ref requires variables to be initialized before being passed to methods. But the out parameter does not require the variable to be initialized before it is passed to the method. But before it returns a value to the calling method, the variable must be initialized in the called method.**   It is also similar to the in keyword, but *in the keyword does not allow the called method to change the parameter value, but *ref* does.**   To use the keyword *out* as a parameter, the keyword *out* must be explicitly used in both method definition and calling method.*   The out parameter is not allowed in asynchronous methods.*   Out parameter is not allowed in iterator method.*   There can be multiple out parameters in a method.*   When the method is called, the out parameter can be declared inline. However, the inline output parameter can be accessed in the same code block it calls.*   Method overloading can also be accomplished using the out parameter.*   Attributes cannot be passed as output parameters because they are not variables.*   Until C# 6.0, the user first declared a variable, and then it could only be passed as an out parameter. However, starting from C# 7.0, in addition to separate variable declarations, users can also declare out variables in the parameter list of method calls.**

****输出参数申报:****

```cs
// No need to initialize 
// the variable here
data_type variable_name;

Method_Name(out variable_name);

// you can also convert both above two 
// lines of codes as follows from
//  C# 7.0 onwards
Method_Name(out data_type variable_name);
```

**这里*变量名*的值必须在被调用的方法中初始化后才能返回值。**

****示例:****

## **C#**

```cs
// C# program to illustrate the
// concept of out parameter
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Declaring variable
        // without assigning value
        int i;

        // Pass variable i to the method
        // using out keyword
        Addition(out i);

        // Display the value i
        Console.WriteLine("The addition of the value is: {0}", i);
    }

    // Method in which out parameter is passed
    // and this method returns the value of
    // the passed parameter
    public static void Addition(out int i)
    {
        i = 30;
        i += i;
    }
}
```

****Output:** 

```cs
The addition of the value is: 60
```** 

****多个 out 参数:**在 C# 中，允许用户向方法传递多个 out 参数，方法返回多个值。**

****示例:**在下面的代码中，我们声明了两个没有初始化的值变量，即 int i，j；。现在我们使用像加法这样的 out 关键字(out i，out j)将这些参数传递给加法方法；。这些变量的值在传递它们的方法中赋值。**

## **c#**

```cs
// C# program to illustrate the
// concept of multiple out parameter
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Declaring variables
        // without assigning values
        int i, j;

        // Pass multiple variable to
        // the method using out keyword
        Addition(out i, out j);

        // Display the value i and j
        Console.WriteLine("The addition of the value is: {0}", i);
        Console.WriteLine("The addition of the value is: {0}", j);
    }

    // Method in which out parameters
    // are passed and this method returns
    // the values of the passed parameters
    public static void Addition(out int p, out int q)
    {
        p = 30;
        q = 40;
        p += p;
        q += q;
    }
}
```

****输出:**

```cs
The addition of the value is: 60
The addition of the value is: 80
```** 

****C# 7.0 中 out 参数的增强:**在 C# 7.0 中，out 参数增加了一些新的特性，这些特性是:**

***   In C # 7.0, the Out parameter can pass withOut declaration and initialization, which is called **embedded declaration** of the out parameter or implicit **type out parameter** . Its scope is limited to the method body, that is, the local scope.*   Out parameter allows [***var***](https://www.geeksforgeeks.org/c-implicitly-typed-local-variables-var/) type to be used in the method parameter list.*   Out parameter, the name of out parameter in definition and call is not necessarily the same.*   It can also be used in trial mode.T21】**

****示例:**下面的程序演示了 Out 参数的内联声明。这里是代码行，即区域(出整数长度，出整数宽度，出整数长度)；包含 Out 参数的内联声明，因为这些变量直接在调用方法内部声明。变量的值在传递它们的方法中初始化。**

****注意:**你需要要求 C# 7.0 版本才能运行这个例子。**

****例:****

## **c#**

```cs
// C# program to illustrate the
// concept of out parameter
using System;

class GFG
{

    // Main method
    static public void Main()
    {

        // In-line declaring variables
        // without assigning values
        // Passing multiple variable to
        // the method using out keyword
        Area(out int length, out int width, out int Rarea);

        // Display the value length, width, and Rarea
        System.Console.WriteLine("Length of the rectangle is: "+ length);
        System.Console.WriteLine("Width of the rectangle is: "+ width);
        System.Console.WriteLine("Area of the rectangle is: "+ Rarea);
        Console.ReadLine();
    }

    // Method in which out parameters are passed
    // and this method returns the values of
    // the passed parameters
    public static void Area(out int p, out int q, out int Rarea)
    {
        p = 30;
        q = 40;
        Rarea = p * q;
    }
}
```

****输出:****

```cs
Length of the rectangle is  : 30
Width of the rectangle is : 40
Area of the rectangle is : 1200
```