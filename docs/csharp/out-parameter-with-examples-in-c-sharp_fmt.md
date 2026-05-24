# 用 C# 中的例子输出参数

> 原文: [https://www.geeksforgeeks.org/out-parameter-with-examples-in-c-sharp/](https://www.geeksforgeeks.org/out-parameter-with-examples-in-c-sharp/)

`out` 是 C# 中的一个关键字，用于将参数作为引用类型传递给方法。它通常在一个方法返回多个值时使用。

## 要点

*   与 `ref` 关键字类似。但 `ref` 和 `out` 关键字的主要区别在于，`ref` 要求变量在传递给方法之前必须被初始化。而 `out` 参数则不需要变量在传递给方法之前被初始化。但在它向调用方法返回一个值之前，该变量必须在被调用的方法中被初始化。
*   它也与 `in` 关键字类似，但 `in` 关键字不允许被调用的方法更改参数值，而 `ref` 允许。
*   要使用 `out` 关键字作为参数，必须在方法定义和调用方法中都显式使用 `out` 关键字。
*   `out` 参数不允许在异步方法中使用。
*   `out` 参数不允许在迭代器方法中使用。
*   一个方法中可以有多个 `out` 参数。
*   调用方法时，可以内联声明 `out` 参数。但是，内联输出参数只能在它被调用的同一个代码块中被访问。
*   也可以使用 `out` 参数实现方法重载。
*   特性不能作为输出参数传递，因为它们不是变量。
*   直到 C# 6.0，用户必须先声明一个变量，然后才能将其作为 `out` 参数传递。然而，从 C# 7.0 开始，除了单独的变量声明外，用户还可以在方法调用的参数列表中声明 `out` 变量。

## 输出参数声明

```cs
// No need to initialize 
// the variable here
data_type variable_name;

Method_Name(out variable_name);

// you can also convert both above two 
// lines of codes as follows from
//  C# 7.0 onwards
Method_Name(out data_type variable_name);
```

这里 `variable_name` 的值必须在被调用的方法中初始化后才能返回值。

## 示例

### C#

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
        int i;

// Pass variable i to the method
        // using out keyword
        Addition(out i);

// Display the value i
        Console.WriteLine("The addition of the value is: {0}", i);
    }

// Method in which out parameter is passed
    // and this method returns the value of
    // the passed parameter
    public static void Addition(out int i)
    {
        i = 30;
        i += i;
    }
}
```

**输出:**

```cs
The addition of the value is: 60
```

## 多个 `out` 参数

在 C# 中，允许用户向方法传递多个 `out` 参数，方法返回多个值。

### 示例

在下面的代码中，我们声明了两个没有初始化的值变量，即 `int i, j`。现在我们使用像 `Addition(out i, out j)` 这样的 `out` 关键字将这些参数传递给 `Addition` 方法。这些变量的值在传递它们的方法中赋值。

### C#

```cs
// C# program to illustrate the
// concept of multiple out parameter
using System;

class GFG {

// Main method
    static public void Main()
    {

// Declaring variables
        // without assigning values
        int i, j;

// Pass multiple variable to
        // the method using out keyword
        Addition(out i, out j);

// Display the value i and j
        Console.WriteLine("The addition of the value is: {0}", i);
        Console.WriteLine("The addition of the value is: {0}", j);
    }

// Method in which out parameters
    // are passed and this method returns
    // the values of the passed parameters
    public static void Addition(out int p, out int q)
    {
        p = 30;
        q = 40;
        p += p;
        q += q;
    }
}
```

**输出:**

```cs
The addition of the value is: 60
The addition of the value is: 80
```

## C# 7.0 中 `out` 参数的增强

在 C# 7.0 中，`out` 参数增加了一些新的特性，这些特性是：

*   在 C# 7.0 中，`out` 参数可以在没有声明和初始化的情况下传递，这被称为 `out` 参数的**内联声明**或隐式类型 `out` 参数。它的作用域仅限于方法体，即局部作用域。
*   `out` 参数允许在方法参数列表中使用 [`var`](https://www.geeksforgeeks.org/c-implicitly-typed-local-variables-var/) 类型。
*   `out` 参数在定义和调用时，名称不一定相同。
*   它也可以在 `try` 模式中使用。

### 示例

下面的程序演示了 `out` 参数的内联声明。这里是代码行，即 `Area(out int length, out int width, out int Rarea)`；包含了 `out` 参数的内联声明，因为这些变量直接在调用方法内部声明。变量的值在传递它们的方法中初始化。

**注意:** 你需要 C# 7.0 版本才能运行这个例子。

### C#

```cs
// C# program to illustrate the
// concept of out parameter
using System;

class GFG
{

// Main method
    static public void Main()
    {

// In-line declaring variables
        // without assigning values
        // Passing multiple variable to
        // the method using out keyword
        Area(out int length, out int width, out int Rarea);

// Display the value length, width, and Rarea
        System.Console.WriteLine("Length of the rectangle is: "+ length);
        System.Console.WriteLine("Width of the rectangle is: "+ width);
        System.Console.WriteLine("Area of the rectangle is: "+ Rarea);
        Console.ReadLine();
    }

// Method in which out parameters are passed
    // and this method returns the values of
    // the passed parameters
    public static void Area(out int p, out int q, out int Rarea)
    {
        p = 30;
        q = 40;
        Rarea = p * q;
    }
}
```

**输出:**

```cs
Length of the rectangle is  : 30
Width of the rectangle is : 40
Area of the rectangle is : 1200
```