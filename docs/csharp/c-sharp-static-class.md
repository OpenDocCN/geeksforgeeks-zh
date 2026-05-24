# C# |静态类

> 原文:[https://www.geeksforgeeks.org/c-sharp-static-class/](https://www.geeksforgeeks.org/c-sharp-static-class/)

在 C# 中，允许使用 *static* 关键字创建一个静态类。静态类只能包含静态数据成员、静态方法和静态构造函数。不允许创建静态类的对象。静态类是 [**封**](https://www.geeksforgeeks.org/c-sealed-class/) ，意思是 ***你不能从另一个类*** 继承一个静态类。

**语法:**

```cs
static class Class_Name
{

      // static data members 
     // static method
}
```

在 C# 中，静态类包含如下两种类型的静态成员:

*   **静态数据成员:**由于静态类总是包含静态数据成员，所以静态数据成员是用 Static 关键字声明的，直接用类名访问。静态数据成员的内存是单独分配的，与对象没有任何关系。
    **语法:**

```cs
static class Class_name 
{
    public static nameofdatamember;
}
```

*   **静态方法:**由于静态类总是包含静态方法，所以静态方法是使用 Static 关键字声明的。这些方法只访问静态数据成员，不能访问非静态数据成员。
    **语法:**

```cs
static class Class_name {

    public static nameofmethod()
    {
         // code 
     }
}
```

**例 1:**

## C#

```cs
// C# program to illustrate the
// concept of static class
using System;

namespace ExampleOfStaticClass {

// Creating static class
// Using static keyword
static class Author {

    // Static data members of Author
    public static string A_name = "Ankita";
    public static string L_name = "CSharp";
    public static int T_no = 84;

    // Static method of Author
    public static void details()
    {
        Console.WriteLine("The details of Author is:");
    }
}

// Driver Class
public class GFG {

    // Main Method
    static public void Main()
    {

        // Calling static method of Author
        Author.details();

        // Accessing the static data members of Author
        Console.WriteLine("Author name : {0} ", Author.A_name);
        Console.WriteLine("Language : {0} ", Author.L_name);
        Console.WriteLine("Total number of articles : {0} ",
                                              Author.T_no);
    }
}
}
```

**Output:** 

```cs
The details of Author is:
Author name : Ankita 
Language : CSharp 
Total number of articles : 84
```