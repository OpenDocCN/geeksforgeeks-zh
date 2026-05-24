# C# |默认构造函数

> 原文:[https://www.geeksforgeeks.org/c-sharp-default-constructor/](https://www.geeksforgeeks.org/c-sharp-default-constructor/)

如果没有为类提供构造函数，C# 会默认创建一个构造函数来实例化对象，并将成员变量设置为默认值，如 **[默认值表](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/default-values-table)** 中所列。没有任何参数的构造函数称为默认构造函数。换句话说，这种类型的构造函数不接受参数。默认构造函数的缺点是类的每个实例将被初始化为相同的值，并且不可能将类的每个实例初始化为不同的值。

**默认构造函数初始化:**

*   All numeric fields in the class are zero.
*   All string and object fields are empty.

**例 1:**

```cs
// C# Program to illustrate the use
// of Default Constructor
using System;

namespace GFG {

class multiplication
{
    int a, b;

    // default Constructor
    public multiplication()   
    {
        a = 10;
        b = 5;
    }

// Main Method
public static void Main() {

    // an object is created, 
    // constructor is called
    multiplication obj = new multiplication(); 

    Console.WriteLine(obj.a);
    Console.WriteLine(obj.b);

    Console.WriteLine("The result of multiplication is: "
                                        +(obj.a * obj.b));
}

}
}
```

**输出:**

```cs
10
5
The result of multiplication is: 50

```

**示例 2:** 在本例中，Person 类没有任何构造函数，在这种情况下，会自动提供默认构造函数，并将字段初始化为默认值。

```cs
// C# Program to illustrate the use
// of Default Constructor
using System;

public class Person
{
    public int age;
    public string name;
}

// Driver Class
class TestPerson {

// Main Method
static void Main() {

    // object creation
    Person pers = new Person();

    Console.WriteLine("Name: {0}, Age: {1}", pers.name, pers.age);

}
} 
```

**输出:**

```cs
Name: , Age: 0

```

**注意:**之所以输出如此，是因为默认情况下字符串赋为 null，整数赋为 0。