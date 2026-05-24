# C# 中的匿名方法

> 原文：[https://www.geeksforgeeks.org/anonymous-method-in-c-sharp/](https://www.geeksforgeeks.org/anonymous-method-in-c-sharp/)

匿名方法是在 *C# 2.0* 中引入的不包含任何名称的方法。当用户想要创建一个内联方法，并且还想像其他方法一样在匿名方法中传递参数时，它非常有用。使用 [`delegate`](https://www.geeksforgeeks.org/c-sharp-delegates/) 关键字定义匿名方法，用户可以将该方法分配给委托类型的变量。

## 语法

```cs
delegate(parameter_list){
    // Code..
};
```

## 示例

```cs
// C# program to illustrate how to 
// create an anonymous function
using System;

class GFG {

    public delegate void petanim(string pet);

    // Main method
    static public void Main()
    {
        // An anonymous method with one parameter
        petanim p = delegate(string mypet)
        {
            Console.WriteLine("My favorite pet is: {0}", mypet);
        };
        p("Dog");
    }
}
```

**输出：**

```cs
My favorite pet is: Dog
```

## 要点

*   这种方法也被称为*内联委托*。
*   使用此方法，您可以创建委托对象，而无需编写单独的方法。
*   此方法可以访问外部方法中存在的变量。此类变量被称为*外部变量*。如下例所示，`fav` 就是一个外部变量。

**示例：**

```cs
// C# program to illustrate how an 
// anonymous function access variable
// defined in outer method
using System;

class GFG {

    // Create a delegate
    public delegate void petanim(string pet);

    // Main method
    static public void Main()
    {
        string fav = "Rabbit";

        // Anonymous method with one parameter
        petanim p = delegate(string mypet)
        {
            Console.WriteLine("My favorite pet is {0}.", mypet);

            // Accessing variable defined
            // outside the anonymous function
            Console.WriteLine("And I like {0} also.", fav);
        };
        p("Dog");
    }
}
```

**输出：**

```cs
My favorite pet is Dog.
And I like Rabbit also.
```

*   您可以将此方法传递给另一个接受委托作为参数的方法。如下例所示：

**示例：**

```cs
// C# program to illustrate how an 
// anonymous method passed as a parameter
using System;

public delegate void Show(string x);

class GFG {

    // identity method with two parameters
    public static void identity(Show mypet, string color)
    {
        color = " Black" + color;
        mypet(color);
    }

    // Main method
    static public void Main()
    {
        // Here anonymous method pass as 
        // a parameter in identity method
        identity(delegate(string color) { 
            Console.WriteLine("The color of my dog is {0}", color); 
        }, "White");
    }
}
```

**输出：**

```cs
The color of my dog is  BlackWhite
```

*   在匿名方法中，参数列表可以被省略，这意味着匿名方法可以被转换为委托。
*   匿名方法块指的是匿名方法中参数的作用范围。
*   匿名方法不包含 `goto`、`break` 或 `continue` 等跳转语句。
*   匿名方法不访问不安全代码。
*   匿名方法不访问外部作用域的 `in`、`ref` 和 `out` 参数。
*   您不能在 `is` 运算符的左侧使用匿名方法。
*   也可以使用匿名方法作为事件处理程序。

**示例：**

```cs
// C# program to illustrate how an 
// anonymous method use as a 
// event handler
MyButton.Click += delegate(Object obj, EventArgs ev)
{
    System.Windows.Forms.MessageBox.Show("Complete without error...!!");
};
```