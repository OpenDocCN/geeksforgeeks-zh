# c# 中的λ表达式

> 原文:[https://www . geesforgeks . org/lambda-expressions-in-c-sharp/](https://www.geeksforgeeks.org/lambda-expressions-in-c-sharp/)

C# 中的 Lambda 表达式像[匿名函数](https://www.geeksforgeeks.org/anonymous-method-in-c-sharp/)一样使用，不同的是在 Lambda 表达式中，您不需要指定您输入的值的类型，因此使用起来更加灵活。
运算符“= >”是所有 lambda 表达式中使用的 lambda 运算符。Lambda 表达式分为两部分，左侧是输入，右侧是表达式。

**λ表达式可以有两种类型:**

*   **表达式λ:**由输入和表达式组成。
    *语法:*

```cs
input => expression;
```

*   **语句 Lambda:** 由输入和一组要执行的语句组成。
    *语法:*

```cs
input => { statements };
```

让我们举一些例子来更好地理解上面的概念。

**示例 1:** 在下面给出的代码中，我们有一个整数列表。第一个 lambda 表达式计算每个元素的平方{ x = > x*x }，第二个用于查找哪些值可以被 3 { x = > (x % 3) == 0 }整除。foreach 循环用于显示。

## C#

```cs
// C# program to illustrate the
// Lambda Expression
using System;
using System.Collections.Generic;
using System.Linq;

namespace Lambda_Expressions {
class Program {
    static void Main(string[] args)
    {
        // List to store numbers
        List<int> numbers = new List<int>() {36, 71, 12,
                             15, 29, 18, 27, 17, 9, 34};

        // foreach loop to display the list
        Console.Write("The list : ");
        foreach(var value in numbers)
        {
            Console.Write("{0} ", value);
        }
        Console.WriteLine();

        // Using lambda expression
        // to calculate square of
        // each value in the list
        var square = numbers.Select(x => x * x);

        // foreach loop to display squares
        Console.Write("Squares : ");
        foreach(var value in square)
        {
            Console.Write("{0} ", value);
        }
        Console.WriteLine();

        // Using Lambda expression to
        // find all numbers in the list
        // divisible by 3
        List<int> divBy3 = numbers.FindAll(x => (x % 3) == 0);

        // foreach loop to display divBy3
        Console.Write("Numbers Divisible by 3 : ");
        foreach(var value in divBy3)
        {
            Console.Write("{0} ", value);
        }
        Console.WriteLine();
    }
}
}
```

**Output:** 

```cs
The list : 36 71 12 15 29 18 27 17 9 34 
Squares : 1296 5041 144 225 841 324 729 289 81 1156 
Numbers Divisible by 3 : 36 12 15 18 27 9 
```

**示例 2:** Lambda 表达式也可以用于用户定义的类。下面给出的代码显示了如何根据定义列表的类的属性对列表进行排序。

## C#

```cs
// C# program to illustrate the
// Lambda Expression
using System;
using System.Collections.Generic;
using System.Linq;

// User defined class Student
class Student {

    // properties rollNo and name
    public int rollNo
    {
        get;
        set;
    }

    public string name
    {
        get;
        set;
    }
}

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // List with eah element of type Student
        List<Student> details = new List<Student>() {
            new Student{ rollNo = 1, name = "Liza" },
                new Student{ rollNo = 2, name = "Stewart" },
                new Student{ rollNo = 3, name = "Tina" },
                new Student{ rollNo = 4, name = "Stefani" },
                new Student { rollNo = 5, name = "Trish" }
        };

        // To sort the details list
        // based on name of student
        // in ascending order
        var newDetails = details.OrderBy(x => x.name);

        foreach(var value in newDetails)
        {
            Console.WriteLine(value.rollNo + " " + value.name);
        }
    }
}
```

**Output:** 

```cs
1 Liza
4 Stefani
2 Stewart
3 Tina
5 Trish
```