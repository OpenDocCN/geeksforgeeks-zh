# C# |可选参数

> 原文:[https://www.geeksforgeeks.org/c-sharp-optional-parameters/](https://www.geeksforgeeks.org/c-sharp-optional-parameters/)

顾名思义，可选参数不是强制参数，它们是可选的。它有助于排除某些参数的参数。或者我们可以说在可选参数中，没有必要传递方法中的所有参数。这个概念是在 *C# 4.0* 中引入的。

**要点:**

*   您可以在 [**方法**](https://www.geeksforgeeks.org/c-sharp-methods/) 、 **[构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)** 、 **[索引器](https://www.geeksforgeeks.org/c-sharp-indexers/)** 和 **[委托](https://www.geeksforgeeks.org/c-sharp-delegates/)** 中使用可选参数。
*   每个可选参数都包含一个默认值，这是其定义的一部分。
*   如果我们不向可选参数传递任何参数，那么它将采用默认值。
*   可选参数的默认值是常量表达式。
*   可选参数总是在参数列表的末尾定义。或者换句话说，方法、构造函数等的最后一个参数。是可选参数。

**示例:**

> 静态公共空学者(string fname，string lname，int age = 20，string branch =“Computer Science”)

在上例中，*int age = 20**string branch = " Computer Science "*为可选参数，有默认值。让我们借助一个例子来讨论可选参数的概念。

```cs
// C# program to illustrate the
// concept of optional parameters
using System;

class GFG {

    // This method contains two regular
    // parameters, i.e. fname and lname
    // And two optional parameters, i.e.
    // age and branch
    static public void scholar(string fname, 
                               string lname,
                               int age = 20,
         string branch = "Computer science")

    {
        Console.WriteLine("First name: {0}", fname);
        Console.WriteLine("Last name: {0}", lname);
        Console.WriteLine("Age: {0}", age);
        Console.WriteLine("Branch: {0}", branch);
    }

    // Main Method
    static public void Main()
    {

        // Calling the scholar method
        scholar("Ankita", "Saini");
        scholar("Siya", "Joshi", 30);
        scholar("Rohan", "Joshi", 37,
           "Information Technology");
    }
}
```

**输出:**

```cs
First name: Ankita
Last name: Saini
Age: 20
Branch: Computer science
First name: Siya
Last name: Joshi
Age: 30
Branch: Computer science
First name: Rohan
Last name: Joshi
Age: 37
Branch: Information Technology

```

**说明:**在上例中，*学者*方法包含四个参数，这四个参数中两个是常规参数，即 *fname* 和 *lname* ，两个是可选参数，即*年龄*和*分支*。这些可选参数包含它们的默认值。当您不传递这些参数的值时，可选参数将使用它们的默认值。当您传递可选参数的参数时，它们将采用传递的值，而不是默认值。

**如果我们使用最后一个参数以外的可选参数会发生什么？**

它会给出编译时错误“*可选参数不能在必需参数*之前”，因为可选参数总是在参数列表的末尾定义。或者换句话说，方法、构造函数等的最后一个参数。是可选参数。

**示例:**

```cs
// C# program to illustrate the concept
// of optional parameters
using System;

class GFG {

    // This method contains two regular
    // parameters, i.e. fname and lname
    // And one optional parameters, i.e. age
    static public void scholar(string fname,
                 int age = 20, string lname)
    {
        Console.WriteLine("First name: {0}", fname);
        Console.WriteLine("Last name: {0}", lname);
        Console.WriteLine("Age: {0}", age);
    }

    // Main Method
    static public void Main()
    {

        // Calling the scholar method
        scholar("Ankita", "Saini");
    }
}
```

**编译时错误:**

> prog.cs(11，26):错误 CS1737:可选参数不能在必需参数之前