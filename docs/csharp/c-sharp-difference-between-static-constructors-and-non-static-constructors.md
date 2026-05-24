# C# |静态构造函数和非静态构造函数的区别

> 原文:[https://www . geeksforgeeks . org/c-静态构造函数和非静态构造函数之间的明显差异/](https://www.geeksforgeeks.org/c-sharp-difference-between-static-constructors-and-non-static-constructors/)

#### 先决条件:[c# 中的构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)

静态构造函数用于初始化类的静态成员，并在创建类的第一个实例之前隐式调用。非静态构造函数用于初始化类的非静态成员。下面是静态构造函数和非静态构造函数之间的区别。

*   **声明:**静态构造函数使用**静态修饰符**显式声明，而所有其他剩余的构造函数是非静态构造函数。非静态构造函数也可以被称为**实例构造函数**，因为它们需要实例来执行。
    **例:**

## C#

```cs
// C# Program to demonstrate
// how to declare the static
// constructor and non-static
// constructor
using System;

class Geeks{

// Static variable
static int s;

// Non-static variable
int ns;

// Declaration of
// static constructor
static Geeks()
{
    Console.WriteLine("It is static constructor");
}

// Declaration of
// non-static constructor
public Geeks()
{
    Console.WriteLine("It is non-static constructor");
}

// Main Method
static void Main(string[] args)
{

    // Static constructor will call implicitly
    // as soon as the class start to execute
    // the first block of code to execute
    // will be static constructor

    // Calling non-static constructor
    Geeks obj1 = new Geeks();
}
}
```

**输出:**

```cs
It is static constructor
It is non-static constructor
```

*   **调用:**静态构造函数总是被隐式调用，但非静态构造函数被显式调用，即通过创建类的实例。
    **例:**在上面的程序中，我们有静态构造函数即 **static Geeks()** ，在主方法中隐式调用。请仔细查看输出，静态构造函数内部的代码正在执行。但是要调用非静态构造函数，即 **Geeks()** ，需要创建类的一个实例，即 *obj1* 。所以对象的创建就是显式调用非静态构造函数。
*   **执行:**静态构造函数在类开始执行时立即执行，它是在类下运行的第一个代码块。但是非静态构造函数只在类的实例创建之后执行。每次创建类的实例时，它都会调用非静态构造函数。
    T3】例:

## C#

```cs
// C# Program to demonstrate
// the execution of static
// constructor and non-static
// constructor
using System;

class Geeks{

// Declaration of
// static constructor
static Geeks()
{
    Console.WriteLine("Static constructor");
}

// Declaration of
// non-static constructor
public Geeks()
{
    Console.WriteLine("Non-Static constructor");
}

// Main Method
static void Main(string[] args)
{

    // static constructor will call implicitly
    // as soon as the class start to execute
    // the first block of code to execute
    // inside the class will be static
    // constructor

    // calling non-static constructor
    // here we are calling non-static
    // constructor twice as we are
    // creating two objects
    Geeks obj1 = new Geeks();
    Geeks obj2 = new Geeks();
}
}
```

**输出:**

```cs
Static constructor
Non-Static constructor
Non-Static constructor
```

*   **说明:**在上面的程序中，创建了*极客()*类的两个对象，即 *obj1* 和 *obj2* 。obj1 和 obj2 将调用非静态构造函数两次，因为每次创建类的实例时，它都会调用非静态构造函数。虽然在 Main 方法(程序的入口点)中，第一个语句是“*Geeks obj 1 = new Geeks()；*“但是一旦编译器找到 Main Method，控制将转移到类，静态块将首先被执行。这就是为什么在输出中可以看到首先调用*静态构造器*。
*   **执行次数:**静态构造函数在一个类的整个生命周期中总是执行一次。但是，如果没有创建类的实例，非静态构造函数可以执行零次，如果创建了 n 个实例，则可以执行 n 次。
    **示例:**在上面的程序中，您可以看到静态构造函数只执行了一次，但是非静态构造函数在创建类的两个实例时执行了两次。如果不创建类的实例，那么非静态构造函数将不会执行。
*   **字段初始化:**静态构造函数用于初始化静态字段，非静态构造函数用于初始化非静态字段。
    T3】例:

## C#

```cs
// C# Program to demonstrate
// initialization of fields
// by using static constructor
// and non-static constructor
using System;

class Geeks{

// Static variable
static int s;

// Non-static variable
int ns;

// Declaration of
// static constructor
static Geeks()
{
    Console.WriteLine("Static constructor");
}

// Declaration of
// non-static constructor
public Geeks()
{
    Console.WriteLine("Non-Static constructor");
}

// Main Method
static void Main(string[] args)
{

    // Static fields can
    // be accessed directly
    Console.WriteLine("Value of s is: " + s);

    // Calling non-static constructor
    Geeks obj1 = new Geeks();

    // Printing the value
    // of non-static field
    Console.WriteLine("Value of ns is: " + obj1.ns);
}
}
```

**输出:**

```cs
Static constructor
Value of s is: 0
Non-Static constructor
Value of ns is: 0
```

*   **说明:**这里静态和非静态字段都是用默认值初始化的。int 类型的默认值为零。静态构造函数将只初始化静态字段。这里的静场是*的*。而非静态字段( *ns* )由非静态构造函数初始化。
*   **参数:**我们不能将任何参数传递给静态构造函数，因为这些参数是隐式调用的，对于传递参数，我们必须显式调用，这是不可能的。它将给出如下例所示的运行时错误。但是，我们可以将参数传递给非静态构造函数。
    T3】例:

## C#

```cs
// C# Program to demonstrate
// the passing of parameters
// to constructor
using System;

class Geeks {

    // static variable
    static int s;

    // non-static variable
    int ns;

    // declaration of
    // static constructor
    // and passing parameter
    // to static constructor
    static Geeks(int k)
    {

        k = s;
        Console.WriteLine("Static constructor & K = " + k);
    }

    // declaration of
    // non-static constructor
    Geeks()
    {
        Console.WriteLine("Non-Static constructor");
    }

    // Main Method
    static void Main(string[] args)
    {
    }
}
```

**运行时错误:**

> prog.cs(18，16):错误 CS0132: `Geeks.Geeks(int)':静态构造函数必须无参数

*   **重载:**可以重载非静态构造函数，但不能重载静态构造函数。重载是在参数标准上完成的。因此，如果您不能将参数传递给静态构造函数，那么我们就不能重载它。
*   **构造函数将是隐式的情况:**如果用户没有定义任何显式构造函数，除了静态类(只包含静态成员)之外的每个类总是包含一个隐式构造函数。如果类包含任何静态字段，那么静态构造函数是隐式定义的。