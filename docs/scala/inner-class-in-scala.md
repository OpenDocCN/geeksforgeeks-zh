# Scala 中的内部类

> 原文:[https://www.geeksforgeeks.org/inner-class-in-scala/](https://www.geeksforgeeks.org/inner-class-in-scala/)

***内部类****意味着将一个类定义为另一个类。该特性使用户能够对仅在一个地方使用的类进行逻辑分组，从而增加了**封装**的使用，并创建了更具可读性和可维护性的代码。在 Scala 中，**内部类**的概念与 Java 不同。就像在 Java 中，内部类是外部类的成员，但是在 Scala 中，内部类绑定到**外部对象**。
**语法:***

```scala
*class Outer_class{
class Inner_class{
// Code..
}
}*
```

***示例:***

```scala
*// Scala program to illustrate how to 
// create inner class

// Outer class
class Geek
{

    // Inner class
    class G1
    {
        var a = 0
        def method()
        {
            for(a<-0 to 3)
            {
                println("Welcome to inner class: G1");
            }
        }
    }
}
object Main 
{
    def main(args: Array[String]) 
    {

        // Creating object of the outer and
        // inner class Here, G1 class is 
        // bounded with the object of Geek class
        val obj = new Geek();
        val o = new obj.G1;
        o.method();
    }
}*
```

***输出:***

```scala
*Welcome to inner class: G1
Welcome to inner class: G1
Welcome to inner class: G1
Welcome to inner class: G1* 
```

***说明:**上例中，Geek 是外层阶级，G1 是内层阶级。现在，要创建内部类的对象，首先需要创建外部类的对象，外部类的对象是 obj。现在，obj 以 G1 类为前缀，创建 G1 类的对象 o，因为内部类绑定到外部类的对象。*

#### *如何在对象内部创建类，在类内部创建对象*

*在 Scala 中，我们还可以在对象中包含一个类，或者在类中包含一个对象。我们用一个例子来讨论一下。在下面的示例中，首先，我们在一个类中创建一个对象，并借助 new 关键字访问该对象的方法，该关键字后跟类名、对象名和方法名，如下语句所示:*

```scala
*new outer_class().inner_object.method;*
```

*现在，第二，我们在一个对象内部创建一个类，并使用 new 关键字后跟对象名、类名和方法名来访问该类中存在的方法，如下面的语句所示:*

```scala
*new outer_object.inner_class().method;* 
```

***示例:***

```scala
*// Scala program to illustrate how to 
// create an object inside a class, Or
// a class inside an object

// Class inside Object
class outer_class
{
    object inner_object
    {
        val q = 0;
        def method()
        {
            for(q <- 0 to 2)
            {
                println("object inside a class example")
            }
            println()
        }
    }
}

// Object inside Class
object outer_object
{
    class inner_class
    {
        val s = 0;
        def method()
        {
            for(s <- 0 to 2)
            {
                println("class inside an object example")
            }
        }
    }
}

object Main
{

    // Main method
    def main(args: Array[String])
    {

        // Object inside a class
        new outer_class().inner_object.method;

        // Class inside an object
        new outer_object.inner_class().method;
    }
}*
```

***输出:***

```scala
*object inside a class example
object inside a class example
object inside a class example

class inside an object example
class inside an object example
class inside an object example* 
```