# C# |操作符重载

> 原文:[https://www.geeksforgeeks.org/c-sharp-operator-overloading/](https://www.geeksforgeeks.org/c-sharp-operator-overloading/)

#### 前提条件:[c# 中的操作符](https://www.geeksforgeeks.org/c-operators/)

函数重载的概念也可以应用于 [**操作符**](https://www.geeksforgeeks.org/c-operators/) 。运算符重载提供了使用同一个运算符进行各种操作的能力。当应用于用户定义的数据类型时，它为 [**C#**](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 运算符提供了额外的功能。它支持用户定义各种操作的实现，其中一个或两个操作数属于用户定义的类。只能重载预定义的一组 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 操作符。对用户定义的数据类型进行操作不像对内置数据类型进行操作那么简单。要将运算符用于用户定义的数据类型，需要根据程序员的要求重载它们。通过给运算符定义一个函数，它可以被重载。使用**运算符关键字**来声明运算符的功能。

**语法:**

```cs
access specifier  className  operator Operator_symbol (parameters)
{
    // Code
}
```

**注意:**运算符重载基本上是为理想的 C# 运算符 w.r.t .提供特殊含义的机制，这是一种用户定义的数据类型，如结构或类。

**下表描述了 C# 中可用的各种运算符的重载能力:**

<figure class="table">

| 经营者 | 描述 |
| --- | --- |
| **+、-、！、~、++、––** | 一元运算符取一个操作数，可以重载。 |
| **+、-、*、/、%** | 二元运算符取两个操作数，可以重载。 |
| **==，！=，=** | 比较运算符可以重载。 |
| **&&、&# 124;&# 124;** | 条件逻辑运算符不能直接重载 |
| **+=、-+、*=、/=、%=、=** | 赋值运算符不能重载。 |

</figure>

### 重载一元运算符

返回类型可以是除 void 之外的任何类型，例如！、~、+和点(。)但返回类型必须是–和++运算符的“类型”类型，并且必须是 true 和 false 运算符的 bool 类型。但是请记住，真运算符和假运算符只能成对重载。如果一个类声明了这些运算符中的一个而没有声明另一个，就会出现编译错误。

以下语法显示了一元运算符–

```cs
operator (object); 
here, operator is a symbol that denotes a unary operator. 
operator a; 
```

的使用

**例:**

```cs
Input : 15, -25
Output : -15, 25

Input : -22, 18
Output : 22, -18 
```

## c#

```cs
// C# program to illustrate the
// unary operator overloading
using System;
namespace Calculator {

class Calculator {

    public int number1 , number2;
    public Calculator(int num1 , int num2)
    {
        number1 = num1;
        number2 = num2;
    }

// Function to perform operation
// By changing sign of integers
public static Calculator operator -(Calculator c1)
{
    c1.number1 = -c1.number1;
    c1.number2 = -c1.number2;
    return c1;
}

// Function to print the numbers
public void Print()
{
    Console.WriteLine ("Number1 = " + number1);
    Console.WriteLine ("Number2 = " + number2);
}
}

class EntryPoint
{

    // Driver Code
    static void Main(String []args)
    {

        // using overloaded - operator
        // with the class object
        Calculator calc = new Calculator(15, -25);

        calc = -calc;

        // To display the result
        calc.Print();
    }
}
}
```

**输出:**

```cs
Number1 = -15
Number2 = 25
```

### 重载二进制运算符

二进制运算符将使用两个操作数。二进制运算符的例子包括 [**算术运算符**](https://www.geeksforgeeks.org/c-operators/# Arithmetic%20Operators) (+、-、*、/、%)、算术赋值运算符(+=、-+、*=、/+、%=)和 [**关系运算符**](https://www.geeksforgeeks.org/c-operators/# Relational%20Operators) 等。重载二元运算符类似于重载一元运算符，只是二元运算符需要一个附加参数。

**语法:**

```cs
operator operator (object1, object2); 
Here, second "operator" is a symbol that 
denotes a binary operator. 
operator + (a, b); 
```

**例:**

```cs
Input : 200, 40
Output : 240

Input : 300, 20 
Output : 320 
```

## c#

```cs
// C# program to illustrate the
// Binary Operator Overloading
using System;
namespace BinaryOverload {

class Calculator {

    public int number = 0;

    // no-argument constructor
    public Calculator() {}

    // parameterized constructor
    public Calculator(int n)
    {
        number = n;
    }

    // Overloading of Binary "+" operator
    public static Calculator operator + (Calculator Calc1,
                                         Calculator Calc2)
    {
        Calculator Calc3 = new Calculator(0);
        Calc3.number = Calc2.number + Calc1.number;
        return Calc3;
    }

    // function to display result
    public void display()
    {
        Console.WriteLine("{0}", number);
    }
}

class CalNum {

    // Driver Code
    static void Main(string[] args)
    {

        Calculator num1 = new Calculator(200);
        Calculator num2 = new Calculator(40);
        Calculator num3 = new Calculator();

        num3 = num1 + num2;

        num1.display(); // Displays 200

        num2.display(); // Displays 40

        num3.display(); // Displays 240

    }
}
}
```

**输出:**

```cs
200
40
240
```

**运算符重载的好处:**

*   Operator overloading provides additional functions for [**C #**](https://www.geeksforgeeks.org/introduction-to-c-sharp/) operator when applied to user-defined data types.
*   Operators can be regarded as functions inside the compiler.