# C# 程序重载一元递增(++)和递减(–)运算符

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-overload-一元-递增-递减-运算符/](https://www.geeksforgeeks.org/c-sharp-program-to-overload-unary-increment-and-decrement-operators/)

在 C# 中，[重载](https://www.geeksforgeeks.org/c-sharp-method-overloading/)是实现多态的常用方式。它是以多种形式重新定义函数的能力。用户可以通过在一个类中定义两个或多个具有相同名称但不同方法签名的方法来实现方法重载。因此，在本文中，我们将学习如何重载一元递增和递减运算符。

### 重载递减运算符

在 C# 中，递减运算符(–)用于将整数值递减 1。它有两种类型:前递减运算符和后递减运算符。当此运算符位于任何变量名之前时，这种类型的运算符称为前递减运算符，例如-y，而当运算符位于任何变量名之后时，这种类型的运算符称为后递减运算符，例如 y–。我们还可以使用以下语法重载减量运算符。这里，我们将对象作为参数传递，然后将递减值设置为对象值，该方法将返回递减值。

**语法:**

```cs
public static GFG operator --(GFG obj)
{
    obj.value = --obj.value;
    return obj;
}
```

**示例:**

```cs
Input  : 50
Output : 49

Input  : 79
Output : 78
```

**示例:**

## C#

```cs
// C# program to demonstrate overloading decrement operator
using System;

class GFG{

// Declare integer variable
private int value;

// Initialize data members
public GFG(int value){this.value = value;}

// Overload unary decrement operator
public static GFG operator--(GFG obj)
{
    obj.value = --obj.value;
    return obj;
}

// Display method to display the value
public void Display()
{
    Console.WriteLine("Values : " + value);
    Console.WriteLine();
}
}

class Geeks{

// Driver code
static void Main(string[] args)
{

    // Declare the object and assign
    // the value to 50
    GFG obj = new GFG(50);

    // Call the unary decrement overload method
    obj--;

    // Call the display method
    obj.Display();
}
}
```

**输出:**

```cs
Values : 49
```

### 霸王增量算子

在 C# 中，递增运算符(++)用于将整数值递增 1。它有两种类型:前增量运算符和后增量运算符。当这个运算符放在任何变量名之前时，这种类型的运算符称为前增量运算符，例如+++y，而当该运算符放在任何变量名之后时，这种类型的运算符称为后增量运算符，例如 y++。我们还可以使用以下语法重载增量运算符。这里，我们将对象作为参数传递，然后将增量值设置为对象值，该方法将返回增量值。

**语法:**

```cs
public static GFG operator ++(GFG obj)
{
    obj.value = ++obj.value;
    return obj;
}
```

**示例:**

```cs
Input  : 50
Output : 51

Input  : 79
Output : 80
```

**示例:**

## C#

```cs
// C# program to demonstrate overloading
// increment operator
using System;

class GFG{

// Declare integer variable
private int value;

// Initialize data members
public GFG(int value)
{
    this.value = value;
}

// Overload unary increment operator
public static GFG operator ++(GFG obj)
{
    obj.value = ++obj.value;
    return obj;
}

// Display method to display the value
public void Display()
{
    Console.WriteLine("Values : " + value);
    Console.WriteLine();
}
}

class Geeks{

// Driver code
static void Main(string[] args)
{

    // Declare the object and assign the value to 50
    GFG obj = new GFG(50);

    // Call the unary increment overload method
    obj++;

    // Call the display method
    obj.Display();
}
}
```

**输出:**

```cs
Values : 51
```