# c# 中 Ref 和 Out 关键字的区别

> 原文:[https://www . geeksforgeeks . org/ref-and-out-difference-关键字-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-ref-and-out-keywords-in-c-sharp/)

**out** 是 C# 中的一个关键字，用于将参数作为引用类型传递给方法。它通常在一个方法返回多个值时使用。out 参数不传递属性。

**例:**

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
        int G;

        // Pass variable G to the method
        // using out keyword
        Sum(out G);

        // Display the value G
        Console.WriteLine("The sum of" + 
                " the value is: {0}", G);
    }

    // Method in which out parameter is passed
    // and this method returns the value of
    // the passed parameter
    public static void Sum(out int G)
    {
        G = 80;
        G += G;
    }
}
```

**输出:**

```cs
The sum of the value is: 160
```

**引用**是 C# 中的一个关键字，用于通过引用传递参数。或者我们可以说，当控件返回到调用方法时，如果在方法的这个参数中进行了任何更改，这些更改将反映在该变量中。*参考*参数没有通过[属性](https://www.geeksforgeeks.org/c-properties/)。

**例:**

```cs
// C# program to illustrate the
// concept of ref parameter
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Assign string value
        string str = "Geek";

        // Pass as a reference parameter
        SetValue(ref str);

        // Display the given string
        Console.WriteLine(str);
    }

    static void SetValue(ref string str1)
    {

        // Check parameter value
        if (str1 == "Geek") {
            Console.WriteLine("Hello!!Geek");
        }

        // Assign the new value
        // of the parameter
        str1 = "GeeksforGeeks";
    }
}
```

**输出:**

```cs
Hello!!Geek
GeeksforGeeks

```

##### 引用关键字和输出关键字之间的差异

| ref 关键字 | out 关键字 |
| 参数在传递给 ref 之前必须初始化。 | 在传递出去之前没有必要初始化参数。 |
| 返回调用方法前不需要初始化参数的值。 | 返回调用方法前需要初始化参数的值。 |
| 通过 ref 参数传递值在被调用的方法还需要改变传递参数的值时很有用。 | 当一个方法返回多个值时，通过 out 参数声明参数非常有用。 |
| 使用 ref 关键字时，数据可能会双向传递。 | 当使用 out 关键字时，数据仅单向传递。 |

**注意:***参考*和*输出*参数在编译时处理相同，但在运行时处理不同。