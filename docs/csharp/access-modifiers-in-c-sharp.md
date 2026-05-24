# c# 中的访问修饰符

> 原文:[https://www.geeksforgeeks.org/access-modifiers-in-c-sharp/](https://www.geeksforgeeks.org/access-modifiers-in-c-sharp/)

访问修饰符是定义程序中成员、类或数据类型的可访问性的关键字。这些主要用于限制外部程序或类不必要的数据操作。有 **4** 访问修饰符(公共、受保护、内部、私有)，其定义了 **6 个可访问性级别**，如下所示:

这些修饰符的可访问性表如下所示:

<figure class="table">

|   | **公共** | **受保护** | **内部** | **受保护内部** | **私人** | **私有受保护** |
| --- | --- | --- | --- | --- | --- | --- |
| **整个程序** | 是 | 不 | 不 | 不 | 不 | 不 |
| **包含类** | 是 | 是 | 是 | 是 | 是 | 是 |
| **电流组件** | 是 | 不 | 是 | 是 | 不 | 不 |
| **衍生类型** | 是 | 是 | 不 | 是 | 不 | 不 |
| **当前组件内的衍生类型** | 是 | 是 | 是 | 是 | 不 | 是 |

</figure>

#### 公共无障碍级别

整个程序都可以访问。这意味着包含类引用的另一个方法或另一个程序集可以访问这些成员或类型。与所有其他访问修饰符相比，此访问修饰符具有最宽松的访问级别。
**语法:**

```cs
public TypeName
```

**例:**在这里，我们声明一个班级*学生*由两个班级成员*组成*和*名字*是公开的。这些成员可以从程序中当前和另一个程序集中的整个代码中的任何位置进行访问。方法 *getRollNo* 和 *getName* 也声明为公开。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to show the use of
// public Access Modifier
using System;

namespace publicAccessModifier {

class Student {

    // Declaring members rollNo
    // and name as public
    public int rollNo;
    public string name;

    // Constructor
    public Student(int r, string n)
    {
        rollNo = r;
        name = n;
    }

    // methods getRollNo and getName
    // also declared as public
    public int getRollNo()
    {
        return rollNo;
    }
    public string getName()
    {
        return name;
    }
}

class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Creating object of the class Student
        Student S = new Student(1, "Astrid");

        // Displaying details directly
        // using the class members
        // accessible through another method
        Console.WriteLine("Roll number: {0}", S.rollNo);
        Console.WriteLine("Name: {0}", S.name);

        Console.WriteLine();

        // Displaying details using
        // member method also public
        Console.WriteLine("Roll number: {0}", S.getRollNo());
        Console.WriteLine("Name: {0}", S.getName());
    }
}
}
```

**Output:** 

```cs
Roll number: 1
Name: Astrid

Roll number: 1
Name: Astrid
```

#### 受保护的可访问性级别

访问仅限于包含此类的成员和派生类型的类。这意味着程序中任何地方的包含类的子类都可以访问受保护的成员。
**语法:**

```cs
protected TypeName
```

**示例:**在下面给出的代码中，类 Y 继承自 X，因此，X 的任何受保护成员都可以从 Y 访问，但不能修改值。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to show the use of
// protected Access Modifier
using System;

namespace protectedAccessModifier {

class X {

    // Member x declared
    // as protected
    protected int x;

    public X()
    {
        x = 10;
    }
}

// class Y inherits the
// class X
class Y : X {

    // Members of Y can access 'x'
    public int getX()
    {
        return x;
    }
}

class Program {

    static void Main(string[] args)
    {
        X obj1 = new X();
        Y obj2 = new Y();

        // Displaying the value of x
        Console.WriteLine("Value of x is : {0}", obj2.getX());
    }
}
}
```

**Output:** 

```cs
Value of x is : 10
```

#### 内部可访问性级别

访问仅限于当前程序集，即声明为内部的任何类或类型都可以在同一命名空间内的任何地方访问。它是 C# 中 ***的默认访问修饰符。
**语法:***** 

```cs
internal TypeName
```

**示例:**在下面给出的代码中，Complex 类是*internaccesmodifier*命名空间的一部分，并且可以在其中访问。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to show use of
// internal access modifier
// Inside the file Program.cs
using System;

namespace internalAccessModifier {

// Declare class Complex as internal
internal class Complex {

    int real;
    int img;

    public void setData(int r, int i)
    {
        real = r;
        img = i;
    }

    public void displayData()
    {
        Console.WriteLine("Real = {0}", real);
        Console.WriteLine("Imaginary = {0}", img);
    }
}

// Driver Class
class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Instantiate the class Complex
        // in separate class but within
        // the same assembly
        Complex c = new Complex();

        // Accessible in class Program
        c.setData(2, 1);
        c.displayData();
    }
}
}
```

**Output:** 

```cs
Real = 2
Imaginary = 1
```