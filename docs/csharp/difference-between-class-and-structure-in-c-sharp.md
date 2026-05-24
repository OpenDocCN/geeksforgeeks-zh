# c# 中类和结构的区别

> 原文:[https://www . geesforgeks . org/c-sharp 中类与结构的区别/](https://www.geeksforgeeks.org/difference-between-class-and-structure-in-c-sharp/)

一个 **[类](https://www.geeksforgeeks.org/c-class-and-object/)** 是一个用户定义的蓝图或原型，从中创建对象。基本上，一个类将字段和方法(定义动作的成员函数)组合成一个单元。

**例:**

```cs
// C# program to illustrate the
// concept of class
using System;

// Class Declaration
public class Author {

    // Data members of class
    public string name;
    public string language;
    public int article_no;
    public int improv_no;

    // Method of class
    public void Details(string name, string language,
                        int article_no, int improv_no)
    {
        this.name = name;
        this.language = language;
        this.article_no = article_no;
        this.improv_no = improv_no;

        Console.WriteLine("The name of the author is :  " + name
                          + "\nThe name of language is : " + language
                          + "\nTotal number of article published  " 
                          + article_no + "\nTotal number of Improvements:"
                          +" done by author is : " + improv_no);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating object
        Author obj = new Author();

        // Calling method of class
        // using class object
        obj.Details("Ankita", "C#", 80, 50);
    }
}
```

**输出:**

```cs
The name of the author is :  Ankita
The name of language is : C#
Total number of article published  80
Total number of Improvements: done by author is : 50

```

**A [结构](https://www.geeksforgeeks.org/c-structures-set-1/)** 是单个单元下不同数据类型变量的集合。它几乎类似于一个类，因为两者都是用户定义的数据类型，并且都持有一堆不同的数据类型。

**例:**

```cs
// C# program to illustrate the
// concept of structure
using System;

// Defining structure
public struct Car
{

    // Declaring different data types
    public string Brand;
    public string Model;
    public string Color;
}

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declare c1 of type Car
        // no need to create an 
        // instance using 'new' keyword
        Car c1;

        // c1's data
        c1.Brand = "Bugatti";
        c1.Model = "Bugatti Veyron EB 16.4";
        c1.Color = "Gray";

        // Displaying the values
        Console.WriteLine("Name of brand: " + c1.Brand + 
                          "\nModel name: " + c1.Model + 
                          "\nColor of car: " + c1.Color);
    }
}
```

**输出:**

```cs
Name of brand: Bugatti
Model name: Bugatti Veyron EB 16.4
Color of car: Gray

```

#### 阶级和结构的区别

| 班级 | 结构 |
| 类是引用类型。 | 结构是值类型。 |
| 所有的引用类型都分配在堆内存上。 | 所有值类型都分配在堆栈内存上。 |
| 配置大引用类型比配置大值类型便宜。 | 与引用类型相比，值类型的分配和取消分配更便宜。 |
| 类具有无限的特性。 | Struct 功能有限。 |
| 类一般用于大型程序。 | Struct 用在小程序中。 |
| 类可以包含构造函数或析构函数。 | 结构不包含无参数构造函数或析构函数，但可以包含参数化构造函数或静态构造函数。 |
| 类使用了新的关键字来创建实例。 | Struct 可以创建一个实例，有或者没有 new 关键字。 |
| 一个类可以从另一个类继承。 | 一个结构不允许从另一个结构或类继承。 |
| 一个类的数据成员可以被保护。 | 结构的数据成员不能被保护。 |
| 类的函数成员可以是虚的也可以是抽象的。 | 结构的函数成员不能是虚拟的或抽象的。 |
| 类的两个变量可以包含对同一对象的引用，对一个变量的任何操作都可以影响另一个变量。 | 结构中的每个变量都包含自己的数据副本(除了 ref 和 out 参数变量)，对一个变量的任何操作都不会影响另一个变量。 |