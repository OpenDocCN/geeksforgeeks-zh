# 如何在 C# 中不使用 is 关键字实现 is 功能

> 原文:[https://www . geeksforgeeks . org/如何在不使用 c-sharp 中的 is-关键字的情况下实现 is-functional/](https://www.geeksforgeeks.org/how-to-implement-is-functionality-without-using-is-keyword-in-c-sharp/)

#### 前提:[为关键字](https://www.geeksforgeeks.org/c-sharp-is-operator-keyword/)[为关键字](https://www.geeksforgeeks.org/c-sharp-as-operator-keyword/)

在实现没有 **is 关键字**的 is 操作之前，让我们简单展望一下 is 关键字实际上是如何工作的。

#### 是关键字

在 C# 中，is 关键字用于在运行时评估兼容性。它确定对象实例或表达式的结果是否可以转换为指定的类型。

**语法:**

```cs
expr is type

```

**示例:**在下面的代码类**中，程序类**继承了一个**类 c1** ，在“如果条件”中，使用 is 运算符检查兼容性，该运算符返回 true。

```cs
// C# program to illustrate the  
// use of 'is' operator keyword 
using System;

namespace GeeksforGeeks {

// Taking an empty class
class c1 {

} 

// Program class inherits c1
class Program : c1 
{

    // Main Method
    static void Main(string[] args)
    {

        // object of Program class
        Program pro1 = new Program(); 

        // dynamic check of compatibility.
        // pro1 is the object of Program class
        // and c1 is class which is inherited by 
        // Program class
        if (pro1 is c1) 
        {
            Console.WriteLine("GeeksForGeeks");
        }
    }
}
}
```

**输出:**

```cs
GeeksForGeeks

```