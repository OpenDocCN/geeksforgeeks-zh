# c# 中的私有构造函数

> 原文:[https://www . geesforgeks . org/private-constructors-in-c-sharp/](https://www.geeksforgeeks.org/private-constructors-in-c-sharp/)

**先决条件:[C# 中的构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)**

私有构造函数是 c# 语言中存在的特殊实例构造函数。基本上，私有构造函数用在只包含静态成员的类中。私有构造函数总是使用`private` 关键字声明的。

**重要点:**

*   它是单例类模式的实现。
*   当类只有静态成员时，使用私有构造函数。
*   使用私有构造函数，可以防止创建该类的实例。
*   如果一个类只包含不带参数的私有构造函数，那么它会阻止默认构造函数的自动生成。
*   如果一个类只包含私有构造函数，而不包含公共构造函数，那么除了嵌套类之外，不允许其他类创建该类的实例。

**语法:**

```cs
private constructor_name
{
   // Code
}

```

**注意:**如果我们不使用任何访问修饰符来定义构造函数，那么编译器会将该构造函数作为私有的。

**例 1:**

```cs
// C# program to illustrate the
// concept of private Constructor
using System;

public class Geeks {

    // Private constructor
    // without parameter
    private Geeks()
    {
        Console.WriteLine("Private Constructor");
    }
}

// Driver Class
class GFG {

    // Main Method
    static void Main() {

        // This line raise error because
        // the constructor is inaccessible
        Geeks obj = new Geeks();
    }
}
```

**编译时错误:**

> prog.cs(40，13):错误 CS0122: `Geeks.Geeks()'由于其保护级别而不可访问

**解释:**在上面的例子中，我们有一个类叫做极客。Geeks 类包含私有构造函数，即`private Geeks()`。在 Main 方法中，当我们试图使用这个语句`Geeks obj = new Geeks();`访问私有构造函数时，编译器会给出一个错误，因为构造函数不可访问。

**例 2:**

```cs
// C# program to illustrate the
// concept of private Constructor
using System;

class Geeks {

    // Variables
    public static string name;
    public static int num;

    // Creating private Constructor
    // using private keyword
    private Geeks() {

        Console.WriteLine("Welcome to Private Constructor");
    }

    // Default Constructor
    // with parameters
    public Geeks(string a, int b) {

        name = a;
        num = b;
    }
}

// Driver Class
class GFG {

    // Main Method
    static void Main() {

        // This line raises error because
        // the constructor is inaccessible
        // Geeks obj1 = new Geeks();

        // Here, the only default 
        // constructor will invoke
        Geeks obj2 = new Geeks("Ankita", 2);

        // Here, the data members of Geeks
        // class are directly accessed
        // because they are static members
        // and static members are accessed 
        // directly with the class name
        Console.WriteLine(Geeks.name + ", " + Geeks.num);
    }
}
```

**输出:**

```cs
Ankita, 2
```

**解释:**上面的例子包含一个名为*极客*的类。这个 Geeks 类包含两个静态变量，即*名称*，和 *num* 以及两个构造函数一个是私有构造函数，即`private Geeks()`，另一个是有两个参数的默认构造函数，即`public Geeks(string a, int b)`。在 Main 方法中，当我们试图使用这个语句调用私有构造函数时`Geeks obj1 = new Geeks();`会给出一个错误，因为私有构造函数不允许创建 Geeks 类的实例。唯一的默认构造函数将调用。