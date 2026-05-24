# C# |复制构造函数

> 原文:[https://www.geeksforgeeks.org/c-sharp-copy-constructor/](https://www.geeksforgeeks.org/c-sharp-copy-constructor/)

通过从另一个对象复制变量来创建对象或将一个对象的数据复制到另一个对象的构造函数称为**复制构造函数**。它是一个参数化构造函数，包含同一类类型的参数。复制[构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)的主要用途是将新实例初始化为现有实例的值。通常情况下，C# 不提供对象的复制构造函数，但是如果你想在你的程序中创建一个复制[构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)，你可以根据你的需求来创建。
**语法:**

```cs
class Class_Name {

        // Parameterized Constructor
        public Class_Name(parameter_list)
        {

            // code

        }

        // Copy Constructor
        public Class_Name(Class_Name instance_of_class)
        {

            // code

        }

    }
```

**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the use
// of copy constructor
using System;

namespace simplecopyconstructor {

class technicalscripter {

    // variables
    private string topic_name;
    private int article_no;

    // parameterized constructor
    public technicalscripter(string topic_name, int article_no)
    {
        this.topic_name = topic_name;
        this.article_no = article_no;
    }

    // copy constructor
    public technicalscripter(technicalscripter tech)
    {
        topic_name = tech.topic_name;
        article_no = tech.article_no;
    }

    // getting the topic name and
    // number of articles published
    public string Data
    {

        get
        {
            return "The name of topic is: " + topic_name +
                   " and number of published article is: " +
                                    article_no.ToString();
        }
    }
}

// Driver Class
public class GFG {

// Main Method
static public void Main()
{

    // creating object t1
    // and provide value to the object
    technicalscripter t1 = new technicalscripter(" C# | Copy Constructor", 38);

    // Creating object t2 and
    // copy the data of t1 object
    // into t2 object
    technicalscripter t2 = new technicalscripter(t1);

    Console.WriteLine(t2.Data);
    Console.ReadLine();
}
}
}
```

**输出:**

```cs
The name of topic is:  C# | Copy Constructor and number of published article is: 38
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to illustrate the use
// of Copy constructor
using System;

namespace copyConstructorExample {

class Vehicle {

    // variables
    private string name;
    private string color;
    private int quantity;

    //  Copy constructor
    public Vehicle(Vehicle a)
    {
        name = a.name;
        color = a.color;
        quantity = a.quantity;
    }

    // Parameterized constructor
    public Vehicle(string name, string color, int quantity)
    {
        this.name = name;
        this.color = color;
        this.quantity = quantity;
    }

    // Get details of Vehicles
    public string DetailsofVehicle
    {
        get
        {
            return "Type: " + name.ToString() +
                   "\nColor: " + color.ToString() +
                   "\nQuantity: " + quantity.ToString();
        }
    }

    // Main Method
    public static void Main()
    {

        // Create a new object.
        Vehicle v1 = new Vehicle("Bike", "Black", 40);

        // here is v1 details are copied to v2.
        Vehicle v2 = new Vehicle(v1);

        Console.WriteLine(v2.DetailsofVehicle);
    }
}
}
```

**输出:**

```cs
Type: Bike
Color: Black
Quantity: 40
```