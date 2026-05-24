# 接口中的 C# |继承

> 原文:[https://www . geeksforgeeks . org/c-sharp-接口继承/](https://www.geeksforgeeks.org/c-sharp-inheritance-in-interfaces/)

C# 允许用户将一个[界面](https://www.geeksforgeeks.org/c-interface/)继承到另一个界面。当一个类实现继承的接口时，它必须提供接口继承链中定义的所有成员的实现。
**要点:**

*   如果一个[类](https://www.geeksforgeeks.org/c-class-and-object/)实现了一个接口，那么就需要实现该接口定义的所有方法，包括基本接口方法。否则，编译器会抛出一个错误。
*   如果派生接口和基接口都声明了同一个成员，则基接口成员名被派生接口成员名隐藏。

**语法:**

```cs
// declaring an interface
access_modifier interface interface_name 
{
   // Your code
}

// inheriting the interface
access_modifier interface interface_name : interface_name
{
    // Your code
}
```

**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the concept
// of inheritance in interface
using System;

// declaring an interface
public interface A {

    // method of interface
    void mymethod1();
    void mymethod2();
}

// The methods of interface A
// is inherited into interface B
public interface B : A {

    // method of interface B
    void mymethod3();
}

// Below class is inheriting
// only interface B
// This class must
// implement both interfaces
class Geeks : B
{

    // implementing the method
    // of interface A
    public void mymethod1()
    {
        Console.WriteLine("Implement method 1");
    }

    // Implement the method
    // of interface A
    public void mymethod2()
    {
        Console.WriteLine("Implement method 2");
    }

    // Implement the method
    // of interface B
    public void mymethod3()
    {
        Console.WriteLine("Implement method 3");
    }
}

// Driver Class
class GFG {

    // Main method
    static void Main(String []args)
    {

        // creating the object
        // class of Geeks
        Geeks obj = new Geeks();

        // calling the method
        // using object 'obj'
        obj.mymethod1();
        obj.mymethod2();
        obj.mymethod3();
    }
}
```

**Output:** 

```cs
Implement method 1
Implement method 2
Implement method 3
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the concept
// of inheritance in the interface
using System;

// declaring an interface
public interface Votes
{

    // method of interface
    void vote_no(int a);
}

// The methods of interface Votes
// is inherited into interface Details
public interface Details : Votes
{

    // method of interface Details
    void detailsofauthor(string n, int p);
}

// Below class is inheriting
// the interface Details
// This class must implement
// the methods of both interface
// i.e. Votes and Details
class TechinalScriptWriter : Details
{

    // implementing the method
    // of interface Votes
    public void vote_no(int a)
    {
        Console.WriteLine("Total number of votes is: {0}", a);
    }

    // implementing the method
    // of interface Details
    public void detailsofauthor(string n, int p)
    {
        Console.WriteLine("Name of the author is: {0}", n);

        Console.WriteLine("Total number of published" +
                                " article is: {0}", p);
    }
}

// Driver Class
class GFG {

    // Main method
    static void Main()
    {

        // Creating the objects of
        // TechinalScriptWriter class
        TechinalScriptWriter obj = new TechinalScriptWriter();

        // calling the methods by passing
        // the required values
        obj.vote_no(470045);
        obj.detailsofauthor("Siya", 98);
    }
}
```

**Output:** 

```cs
Total number of votes is: 470045
Name of the author is: Siya
Total number of published article is: 98
```