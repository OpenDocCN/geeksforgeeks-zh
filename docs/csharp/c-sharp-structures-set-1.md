# C# |结构|集合–1

> 原文:[https://www.geeksforgeeks.org/c-sharp-structures-set-1/](https://www.geeksforgeeks.org/c-sharp-structures-set-1/)

***结构*** 是一个值类型，是单个单元下不同数据类型变量的集合。它几乎类似于一个类，因为两者都是用户定义的数据类型，并且都持有一堆不同的数据类型。C# 提供使用预定义的 [**数据类型**](https://www.geeksforgeeks.org/c-data-types-2/) 的能力。然而，有时用户可能需要定义自己的数据类型，也称为**用户定义的数据类型**。虽然它属于值类型，但用户可以根据需求修改它，这就是为什么它也被称为用户定义的数据类型。
**定义结构:**在 C# 中，使用 ***struct*** 关键字定义结构。使用 struct 关键字可以定义包含不同数据类型的结构。一个结构也可以包含构造函数、常数、字段、方法、属性、索引器和事件等。

*   **语法:**

```cs
Access_Modifier struct structure_name
{

   // Fields 
   // Parameterized constructor 
   // Constants 
   // Properties 
   // Indexers 
   // Events 
   // Methods etc.

}
```

*   **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Declaration of structure
using System;
namespace ConsoleApplication {

// Defining structure
public struct Person
{
    // Declaring different data types
    public string Name;
    public int Age;
    public int Weight;

}

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // Declare P1 of type Person
        Person P1;

        // P1's data
        P1.Name = "Keshav Gupta";
        P1.Age = 21;
        P1.Weight = 80;

        // Displaying the values
        Console.WriteLine("Data Stored in P1 is " +
                           P1.Name + ", age is " +
                           P1.Age + " and weight is " +
                           P1.Weight);

    }
}
}
```

**Output:** 

```cs
Data Stored in P1 is Keshav Gupta, age is 21 and weight is 80
```

*   **说明:**在上面的代码中，用数据成员**名字**、**年龄**和**体重**创建了一个名为**“人”**的结构。在主方法中，创建结构类型“人”的 **P1** 。现在，P1 可以借助**访问其数据成员。(点)操作符**。

**复制结构:**在 C# 中，用户可以使用' = '(赋值)运算符将一个结构对象复制到另一个结构对象中。

*   **语法:**

```cs
Structure_object_destination = structure_object_source;
```

*   **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate copy the structure
using System;
namespace ConsoleApplication {

// Defining structure
public struct Person
{
    // Declaring different data types
    public string Name;
    public int Age;
    public int Weight;

}

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // Declare P1 of type Person
        Person P1;

        // P1's data
        P1.Name = "Keshav Gupta";
        P1.Age = 21;
        P1.Weight = 80;

        // Declare P2 of type Person
        Person P2;

        // Copying the values of P1 into P2
         P2 = P1;

        // Displaying the values of P1
        Console.WriteLine("Values Stored in P1");
        Console.WriteLine("Name: " +P1.Name);
        Console.WriteLine("Age: " +P1.Age);
        Console.WriteLine("Weight: " +P1.Weight);
        Console.WriteLine("");

        // Displaying the values of P2
        Console.WriteLine("Values Stored in P2");
        Console.WriteLine("Name: " +P2.Name);
        Console.WriteLine("Age: " +P2.Age);
        Console.WriteLine("Weight: " +P2.Weight);

    }
}
}
```

**Output:** 

```cs
Values Stored in P1
Name: Keshav Gupta
Age: 21
Weight: 80

Values Stored in P2
Name: Keshav Gupta
Age: 21
Weight: 80
```

*   **说明:**struct Person 的数据成员在 P1 的帮助下初始化，数据成员的值可以由 P1 使用' = '(赋值运算符)复制到 P2。

**结构的嵌套:** C# 允许将一个结构声明为另一个结构，这个概念被称为结构的嵌套。

*   **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate Nesting of structures
using System;
namespace ConsoleApplication {

// first structure defined
// with public modifier
public struct Address
{

    // data member of Address structure
    public string City;
    public string State;
}

// Another structure
struct Person
{

    // data member of Person structure
    public string Name;
    public int Age;

    // Nesting of Address structure
    // by creating A1 of type Address
    public Address A1;
}

class Geeks {

    // Main method
    static void Main(string[] args)
    {

        // Declare p1 of type Person
        Person p1;

        // Assigning values to the variables
        p1.Name = "Raman";
        p1.Age = 12;

        // Assigning values to the nested
        // structure data members
        p1.A1.City = "ABC_City";
        p1.A1.State = "XYZ_State";

        Console.WriteLine("Values Stored in p1");
        Console.WriteLine("Name: " +p1.Name);
        Console.WriteLine("Age: " +p1.Age);
        Console.WriteLine("City: " +p1.A1.City);
        Console.WriteLine("State: " +p1.A1.State);

    }
}
}
```

**Output:** 

```cs
Values Stored in p1
Name: Raman
Age: 12
City: ABC_City
State: XYZ_State
```

**关于结构的要点:**

*   一旦结构超出范围，它就会被自动解除分配。
*   创建比堆类型更容易和更快。
*   使用结构可以很容易地将变量值复制到堆栈上。
*   结构是值类型，而类是引用类型。

**结构和类别的区别:**

<figure class="table">

| 种类 | 结构 | 班级 |
| 数据类型 | 值类型 | 参考类型 |
| 赋值运算 | 复制值 | 复制引用 |
| 无参数构造函数 | 不允许 | 允许 |
| 遗产 | 不支持 | 始终支持 |

</figure>