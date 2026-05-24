# 如何在 C# 中将对象作为参数传递到方法中？

> 原文:[https://www . geeksforgeeks . org/如何将对象作为参数传递给 c-sharp 中的方法/](https://www.geeksforgeeks.org/how-to-pass-an-object-as-an-argument-into-method-in-c-sharp/)

给定一个对象，现在我们将这个对象作为参数传递给 C# 中的方法。这里，方法是包含一系列语句的代码块，这些语句只有在调用方法时才会执行。我们可以将数据以参数的形式传递给方法，对象是一个动态创建的类的实例。基本数据类型可以作为参数传递给 C# 方法，就像对象也可以作为参数传递给方法一样。但是请记住，我们不能在方法中直接传递类对象。我们只能在方法中传递对对象的引用。

```cs
// Creating the demo object
demo d1 = new demo(6);

// Passing object as an argument to the PassObj method.
d1.PassObj(d1);
```

**例 1:**

## c#

```cs
// C# program to pass an object as an argument into method 
using System;

// Creating a class named demo
class demo
{
    int value;

    // Constructor to initialize the variable value
    public demo(int val) 
    {
        value = val;
    }

    // Method in which we pass the object as a argument
    public void PassObj(demo d2)
    {
        Console.WriteLine(d2.value);
    }
}

// Driver code
class GFG{

static void Main()
{

    // Creating the demo object
    demo d1 = new demo(6);

    // Passing object as an argument to 
    // the PassObj method.
    d1.PassObj(d1);
}
}
```

**输出**

```cs
6
```

**解释:**在上面的例子中，首先我们创建一个名为“demo”**的类，用一个构造函数初始化一个整型变量。它还有一个名为 PassObj()的方法，该方法接受一个参数。现在在主函数中，我们创建一个名为“d1”的演示类的对象，然后在 PassObj()方法中传递这个对象，并打印该值。**

****例 2:****

## **c#**

```cs
// C# program to pass two objects as an argument into method 
using System;

class Geeks
{
    int num;

    // Constructor to initialize the variable value
    public Geeks(int val) 
    {
        num = val;
    }

    public void PassObj(Geeks d1, Geeks d2)
    {

        // Multiplying the values of both objects
        Console.WriteLine(d1.num * d2.num);
    }
}

// Driver code
class GFG{

static void Main()
{

    // Creating the demo objects
    Geeks d1 = new Geeks(6);
    Geeks d2 = new Geeks(2);

    // Passing 2 objects as arguments to the 
    // PassObj method and PassObj will print 
    // the product of the two values in the 
    // two objects
    d1.PassObj(d1, d2);
}
}
```

****输出**

```cs
12
```** 

****解释:**在上面的例子中，首先我们创建了一个名为“Geeks”**的类，用构造函数初始化一个整型变量。它还有一个名为 PassObj()的方法，该方法接受两个参数并返回两个值的乘积。现在在主函数中，我们创建了两个名为“d1”和“d2”的 Geeks 类的对象，然后在 PassObj()方法中传递这个对象，并打印出值。****