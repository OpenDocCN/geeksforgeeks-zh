# Scala |字段覆盖

> 原文:[https://www.geeksforgeeks.org/scala-field-overriding/](https://www.geeksforgeeks.org/scala-field-overriding/)

在任何面向对象的编程语言中，Overriding 都是一种特性，它允许子类提供其某个超类已经提供的方法或字段的特定实现。在 Scala 中，与在 Java 中的重写相比，重写被进一步明确地声明，因为这里两种方法以及*字段*都可以被重写，但是它有一些必须遵守的限制。

T3【赛场规则】超越 T5】

字段覆盖的规则如下:

*   One of the most important rules is that we must use the keyword *to cover* or cover symbols when covering superclass fields in subclasses, otherwise the compiler will throw an error and terminate the execution of the program.
*   In order to overwrite with *field, we need to overwrite variables declared only with **val** keyword in superclass and subclass.*
*   Field coverage cannot cover *var* because we can read or write *var* .

现在，让我们看一些例子来说明这些限制。

**例:**

```scala
// Scala program of Field 
// Overriding

// Creating class
class Shapes
{

    // Creating a variable with 
    // val keyword
    val description:String = "shape"
} 

// Creating a subclass
class shape_1 extends Shapes
{ 

    // Overriding field using
    // 'override' keyword 
    override val description:String ="It is a circle."

    // Defining a method
    def display()
    { 

        // Displays output
        println(description) 
    } 
} 

// Creating a subclass
class shape_2 extends Shapes
{ 

    // overriding field using
    // 'override' keyword 
    override val description:String ="It is a square."

    // Defining a method
    def display()
    { 

        // Displays output
        println(description) 
    } 
} 

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    { 

        // Creating instances for all
        // the sub-classes
        var x = new shape_1() 
        var y = new shape_2() 

        // Calling methods
        x.display()
        y.display()

    } 
} 
```

**输出:**

```scala
It is a circle.
It is a square.

```