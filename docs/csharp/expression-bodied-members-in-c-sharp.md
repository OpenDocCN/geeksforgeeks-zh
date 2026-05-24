# c# 中的表达体成员

> 原文:[https://www . geesforgeks . org/expression-body-members-in-c-sharp/](https://www.geeksforgeeks.org/expression-bodied-members-in-c-sharp/)

表达式体成员为定义属性和方法提供了最少且简洁的语法。它有助于消除样板代码，并有助于编写可读性更强的代码。当成员的主体仅由一个表达式组成时，可以使用表达式体语法。它使用 **= >** (箭头处的*)运算符来定义方法或属性的主体，并允许去掉大括号和*返回*关键字。该特性最初是在 C# 6 中引入的。*

### 表达体方法

在 C# 中，[方法](https://www.geeksforgeeks.org/c-sharp-methods/)是执行给定任务并将结果返回给调用者的语句的集合。通常，方法最终只包含一条语句。例如，考虑以下代码:

```cs
int GetRectangleArea(int length, int breadth) 
{
    return length * breadth;
} 
```

上述方法只包含一个返回语句。使用表达式体语法，上述方法可以重写如下:

```cs
int GetRectangleArea(int length, int breadth) => length * breadth;
```

请注意，没有花括号和*返回*语句。已经使用了 **= >** 运算符来代替大括号。*返回*语句后的表达式写在 **= >** 运算符之后。

**语法**

> [access-修饰符][限定符]返回类型 method name([参数]) = >表达式；

**例**

以下示例定义了一个名为 *IsEven()* 的布尔方法，如果传递给它的数字为偶数，则返回 true，否则返回 false。 *IsEven()* 方法使用表达式体语法。

## C#

```cs
// C# program to illustrate expression bodied method
using System;

class GFG{

// Returns true if number is even
// else returns false
public static bool IsEven(int number) => number % 2 == 0;

// Driver code
public static void Main()
{
    int n = 10;

    if (IsEven(n))
    {
          Console.WriteLine("{0} is even", n);
    }
    else 
    {
        Console.WriteLine("{0} is odd", n);
    }
}
}
```

**Output**

```cs
10 is even
```

### 表达式体空方法

Void 方法是那些不包含*返回*语句并且只包含一条语句的方法，也可以使用表达式体语法。例如，以下方法:

```cs
void PrintName(string name)
{
    Console.WriteLine({content}quot;The name is {name}");
}
```

可以用表达式体语法编写，如下所示:

```cs
void PrintName(string name) => Console.WriteLine({content}quot;The name is {name}"); 
```

### 表达体属性

[属性](https://www.geeksforgeeks.org/c-sharp-properties/)访问器也只能有一个语句。有了表达式体属性，这样的属性定义可以简化。

**1。只读属性**

只读属性是只有*获取*访问器的属性，如下所示:

```cs
public int Name 
{ 
    get 
    {
        return "Geeks For Geeks";
    }
}  
```

使用表达式体语法，属性可以定义如下:

```cs
public int Name => "Geeks For Geeks";
```

**语法**

> [access-修饰符][限定符]类型属性名称= >表达式；

**例**

以下示例定义了一个名为 *Square* 的类，其构造函数接受正方形边的长度。一旦在构造函数中设置了边，就不能修改，因为公共*边*属性是只读的。此外，*端*字段是私有的，不能从类外访问。

## C#

```cs
// C# program to illustrate expression bodied properties
using System;

public class Square 
{
    private int side;

    public Square(int side) 
    {
        this.side = side;
    }

    public int Side => side;
}

class GFG{

// Driver code
public static void Main()
{
    var square = new Square(4);
    Console.WriteLine({content}quot;Side is {square.Side}");
}
}
```

**Output**

```cs
Side is 4
```

**2。非只读属性**

从 C# 7 开始，非只读属性也可以有表达式体*获取*和*设置*访问器。在下面的 *Person* 类中， *Name* 属性定义了 *get* 和 *set* 访问器，每个访问器只有一个语句:

```cs
public class Person
{
    private string name;

    public string Name
    {
        get 
        {
            return name;
        }
        set 
        {
           name = value;
        }
    }
}
```

这可以通过使用表达式体访问器来简化:

```cs
public class Person
{
    private string name;

    public string Name
    {
        get => name;
        set => name = value;
    }
}
```

**语法**

> [访问修饰符][限定符][类型]属性名
> 
> {
> 
> get = >表达式；
> 
> 设置= >表达式；
> 
> }

**例**

下面的代码像上面的例子一样定义了一个 *Square* 类，但是在这里，Side 属性也有一个*集*访问器。另外，[对象初始化器](https://www.geeksforgeeks.org/object-and-collection-initializer-in-c-sharp/)代替构造器被用来为*侧*属性提供初始值:

## C#

```cs
// C# program to illustrate expression bodied properties
using System;

public class Square 
{
    private int side;

    public int Side 
    {
        get => side;
        set => side = value;
    }
}

class GFG{

// Driver code    
public static void Main()
{
    var square = new Square{Side = 4};
    Console.WriteLine({content}quot;Side is {square.Side}");
    square.Side = 10;
      Console.WriteLine({content}quot;Side is now {square.Side}");
}
}
```

**Output**

```cs
Side is 4
Side is now 10
```

### 表达式体构造函数和析构函数

表达式体语法也被扩展为与[构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)和[析构函数/终结器](https://www.geeksforgeeks.org/destructors-in-c-sharp/)一起使用。如果这些方法中的任何一个只包含一个语句，它们可以被定义为表达式体。

**语法**

*   构造器

> [access-修饰符]class name([参数]) = >表达式；

*   析构器/终结器

> ~ClassName() = >表示式；

**例**

在下面的例子中， *Square* 类定义了一个构造函数和析构函数，每个都包含一个表达式体定义:

## C#

```cs
// C# program to illustrate expression-bodied 
// constructors and destructors
using System;

public class Square 
{
    private int side;

    public Square(int side) => this.side = side;

    ~Square() => Console.WriteLine("Square's Destructor");

    public int Side => side;
}

class GFG{

// Driver code
public static void Main()
{
    var square = new Square(4);
    Console.WriteLine({content}quot;Side is {square.Side}");
}
}
```

**Output**

```cs
Side is 4
Square's Destructor
```

### 表达式体索引器

类似于属性，[索引器](https://www.geeksforgeeks.org/c-sharp-indexers/)访问器也可以是表达式体。索引器定义遵循与属性相同的约定，这意味着可以在不指定访问器的情况下定义只读索引器，并且读写访问器需要访问器的名称。

**语法**

*   只读索引器

> [access-modifier][qualifier]返回-键入这个[ [parameters] ] = >表达式；

*   读写索引器

> [access-修饰符][限定符]返回-键入此[[参数] ]
> 
> {
> 
> get = >表达式；
> 
> 设置= >表达式；
> 
> }

**例**

下面的类*编程语言*定义了编程语言的字符串数组语言，还定义了一个索引器，该索引器将索引转发到*语言*数组，并返回该索引处的元素(语言)。索引器是只读的，因此不能在类之外修改数组中的语言。

## C#

```cs
// C# program to illustrate expression-bodied indexers
using System;

public class ProgrammingLangs
{
    private string[] languages = 
    {
        "C#",
        "C",
        "C++",
        "Python",
        "Java"
    };

    public string this[int idx] => languages[idx];
}

class GFG{

// Driver code
public static void Main()
{
    var langs = new ProgrammingLangs();
    Console.WriteLine(langs[0]);
      Console.WriteLine(langs[2]);
      Console.WriteLine(langs[3]);
}
}
```

**Output**

```cs
C#
C++
Python
```

### 表达式体算子函数

就像有一个语句的普通方法可以是表达式体一样，如果运算符方法定义的主体由一个语句组成，那么它们也可以是表达式体。

**语法**

> [访问-修饰符]静态运算符[运算符-符号]([参数]) = >表达式；

**例**

以下示例实现了一个 Complex 类，该类表示复数的实部和虚部，并且还定义了二元+运算符，以允许添加两个 *Complex* 对象。*操作符+* 功能是表情体。

## C#

```cs
// C# program to illustrate expression-bodied operator functions
using System;

public struct Complex
{
    public int Real{get; set;}
    public int Imaginary{get; set;}

    public Complex(int real, int imaginary)
    {
        Real = real;
        Imaginary = imaginary;
    }

    // Expression-bodied operator method
    public static Complex operator + (
        Complex c1, Complex c2) =>
        new Complex(c1.Real + c1.Real,
               c1.Imaginary + c2.Imaginary);

    public override string ToString() => 
       {content}quot;({Real}) + ({Imaginary}i)";
}

class GFG{

// Driver code 
public static void Main()
{
    var a = new Complex(3, 2);
    var b = new Complex(1, 2);
    var result = a + b;

    Console.WriteLine({content}quot;{a} + {b} = {result}");
}
}
```

**输出:**

```cs
(3) + (2i) + (1) + (2i) = (6) + (4i)
```