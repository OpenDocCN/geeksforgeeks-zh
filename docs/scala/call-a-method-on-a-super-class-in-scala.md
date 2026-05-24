# 调用 Scala 中一个超类的方法

> 原文:[https://www . geesforgeks . org/call-a-method-on-a-super-class-in-Scala/](https://www.geeksforgeeks.org/call-a-method-on-a-super-class-in-scala/)

当我们想调用超类方法时，就要用到这个概念。因此，每当基类和子类有相同的命名方法时，为了解决歧义，我们使用 **super** 关键字来调用基类方法。关键词**“超”**带着传承的概念来到这里。

下面是在超类上调用方法的例子。

**示例#1:**

```scala
// Scala program to call a method
// on a superclass in Scala

/* Base class ComputerScience */
class ComputerScience
{
    def read 
    {
        println("I'm reading")
    }
    def write
    {
        println("I'm writing")
    }
}

/* Subclass Scala */
class Scala extends ComputerScience
{
    // Note that readThanWrite() is only in Scala class 
    def readThanWrite() 
    {
        // Will invoke or call parent class read() method 
        super.read

        // Will invoke or call parent class write() method 
        super.write
    }
}

// Creating object 
object Geeks
{
    // Main method 
    def main(args: Array[String]) 
    { 
        var ob = new Scala();

        // Calling readThanWrite() of Scala
        ob.readThanWrite();
    } 
} 
```

**输出:**

```scala
I'm reading
I'm writing

```

在上面的例子中，我们使用 **super** 关键字调用超类的多个方法。

**例 2:**

```scala
// Scala program to call a method
// on a superclass in Scala

/* Super class Person */
class Person 
{ 
    def message() 
    { 
        println("This is person class"); 
    } 

} 

/* Subclass Student */
class Student extends Person 
{ 

   override def message()
    { 
        println("This is student class")
    }

    // Note that display() is only in Student class 
    def display() 
    { 
        // will invoke or call current class message() method  
        message ()

        // will invoke or call parent class message() method 
        super.message
    } 
} 

/* Creating object */
object Geeks
{ 
    // Main method
    def main(args: Array[String]) 
    { 
        var s = new Student(); 

        // Calling display() of Student 
        s.display(); 
    } 
} 
```

**输出:**

```scala
This is student class
This is person class

```

在上面的例子中，我们已经看到如果我们只调用方法`message()`，那么当前类`message()`被调用，但是使用 **super** 关键字，super 类的`message()`也可以被调用。