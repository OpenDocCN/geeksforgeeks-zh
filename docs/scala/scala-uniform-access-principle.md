# Scala |统一访问原则

> 原文:[https://www . geesforgeks . org/Scala-uniform-access-principle/](https://www.geeksforgeeks.org/scala-uniform-access-principle/)

在 Scala 中，实现了一个称为**统一访问原则**的编程抽象，该原则声明用于检索类属性的注释对于方法和变量都是等效的。这个原则是由伯特兰·迈耶提出的。这个原则仅仅意味着用于访问一个类的特性的符号不应该因为它是一个方法还是一个属性而不同。
T3【几点注意:

*   使用此原则，没有参数的属性和函数可以通过相同的语法来访问。
*   没有参数的函数的定义可以转换为“var”，反之亦然。
*   这个原则更符合面向对象编程。

**示例:**

```scala
// Scala program for Uniform
// Access Principle

// Creating object
object Access
{

    // Main method
    def main(args: Array[String])
    {

        // Creating array
        val x : Array[Int] = Array(7, 8, 9, 10, 45)

        // Creating String
        val y = "GeeksforGeeks"

        // Accessing length of an 
        // array
        println(x.length)

        // Accessing length of a
        // String
        println(y.length)
    }
}
```

**Output:**

```scala
5
13

```

现在，我们知道数组的长度是一个变量，字符串的长度是类“字符串”中的一个方法，但是我们以相同的方式访问它们。
**例:**

```scala
// Scala program for Uniform
// Access Principle

// Creating object
object Access
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a list
        val x = List(1, 3, 5, 7, 9, 10)

        // Creating a method
        def portal = {

        "Geeks" +"for" + "Geeks"

        }

        // Accessing size of a
        // method
        println(portal.size)

        // Accessing size of a
        // variable
        println(x.size)
    }
}
```

**Output:**

```scala
13
6

```

这里，变量和方法的访问方式也是相同的。