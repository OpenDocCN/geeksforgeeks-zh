# C# |枚举(或枚举)

> 原文:[https://www.geeksforgeeks.org/c-sharp-enumeration-or-enum/](https://www.geeksforgeeks.org/c-sharp-enumeration-or-enum/)

***枚举(或枚举)*** 是 C# 中的一个[值数据类型](https://www.geeksforgeeks.org/c-data-types-2/)。它主要用于将名称或字符串值赋给整型常量，这使得程序易于阅读和维护。例如，一副扑克牌中的 4 套花色可能是 4 个名为 Club、Diamond、Heart 和 Spade 的枚举数，属于名为花色的枚举类型。其他例子包括自然列举的类型(如行星、星期几、颜色、方向等。).枚举的主要目的是定义我们自己的数据类型(枚举数据类型)。枚举是直接在命名空间、类或结构中使用 ***enum*** 关键字声明的。

**语法:**

```cs
enum Enum_variable
{
     string_1...;
     string_2...;
     .
     .
}
```

在上面的语法中，Enum_variable 是枚举器的名称，string_1 附加值 0，string_2 附加值 1，以此类推。因为默认情况下，枚举的第一个成员的值为 0，每个后续枚举成员的值都增加 1。我们可以更改这个默认值。

*   **示例 1:** 考虑下面的枚举代码。这里创建了名为**月**的枚举，它的数据成员是一月、二月、三月、四月、五月等月份的名称。现在让我们尝试打印这些枚举的默认整数值。**从枚举类型转换为整型需要显式强制转换。**

## C#

```cs
// C# program to illustrate the enums
// with their default values
using System;
namespace ConsoleApplication1 {

// making an enumerator 'month'
enum month
{

    // following are the data members
    jan,
    feb,
    mar,
    apr,
    may

}

class Program {

    // Main Method
    static void Main(string[] args)
    {

        // getting the integer values of data members..
        Console.WriteLine("The value of jan in month " +
                          "enum is " + (int)month.jan);
        Console.WriteLine("The value of feb in month " +
                          "enum is " + (int)month.feb);
        Console.WriteLine("The value of mar in month " +
                          "enum is " + (int)month.mar);
        Console.WriteLine("The value of apr in month " +
                          "enum is " + (int)month.apr);
        Console.WriteLine("The value of may in month " +
                          "enum is " + (int)month.may);
    }
}
}
```

**Output:** 

```cs
The value of jan in month enum is 0
The value of feb in month enum is 1
The value of mar in month enum is 2
The value of apr in month enum is 3
The value of may in month enum is 4
```

*   **示例 2:** 在下面的代码中，创建了一个名为 **shapes** 的枚举器，字符串数据成员为 **Circle** ，默认情况下初始化为值 0，类似地， **Square** 在类周长内被赋值为值 1。还有一个成员函数 peri()，它将一个参数作为值来初始化边/半径。另一个参数用于以整数值(0 或 1)的形式判断形状是圆还是方。现在在 main()方法中，创建了一个周长类的对象。在调用 peri()方法时，*周长.形状.圆*表示它是一个值为 0 的圆，类似于值为 1 的*周长.形状.正方形*的情况。因此在该方法中，如果 s1 对象的值为 0，则它是圆，因此计算它的周长，正方形
    周长也是如此。

## C#

```cs
// C# program to illustrate the Enums
using System;
namespace ConsoleApplication2 {

class Perimeter {

    // declaring enum
    public enum shapes
    {
        circle,
        square
    }

    public void peri(int val, shapes s1)
    {

        // checking for shape to be circle
        if (s1 == 0)
        {

            // Output the circumference
            Console.WriteLine("Circumference of the circle is " +
                                                  2 * 3.14 * val);
        }

        else
        {

            // else output the perimeter of the square
            Console.WriteLine("Perimeter of the square is " +
                                                     4 * val);
        }
    }
}

class Program {

    // Main Method
    static void Main(string[] args)
    {

        Perimeter a1 = new Perimeter();
        a1.peri(3, Perimeter.shapes.circle);
        a1.peri(4, Perimeter.shapes.square);

    }
}
}
```

**Output:** 

```cs
Circumference of the circle is 18.84
Perimeter of the square is 16
```