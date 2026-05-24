# Scala |等于

> 原文:[https://www.geeksforgeeks.org/scala-equals/](https://www.geeksforgeeks.org/scala-equals/)

**等于**是一个特性，这是一个容纳相等功能的链接。它扩展了类*任意*。这里的线性超类型是任意的，这里的子类是产品、产品 1、产品 2 以及更多。
**抽象值成员**
这里的抽象值成员是:

```scala
abstract def canEqual(that: Any): Boolean
```

如果所述实例相等，则返回真。
**例:**

```scala
// Scala program of trait 
// Equals

// Creating a case class of 
// employee
case class Employee (name:String, age:Int) 

// Creating object
object Main 
{ 
    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating objects
        var c = Employee("Nidhi", 23) 
        var d = Employee("Nidhi", 23)
        var e = Employee("Nidhi", 25)

        // Displays true if instances 
        // are equal else false
        println(c.canEqual(d))
        println(c.canEqual(e))

    } 
} 
```

**Output:**

```scala
true
true

```

这里，我们使用了**caneqal**方法来证明实例的相等性。

**示例:**

```scala
// Scala program of trait 
// Equals

// Creating a case class of 
// Name
case class Name (firstname:String, lastname:String) 

// Creating object
object Main 
{ 
    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating objects
        var x = Name("Nidhi", "Singh") 
        var y = Name("Nidhi", "Singh")
        var z = Name("Geeta", "Sharma")

        // Displays true if instances 
        // are equal else false
        println(x.equals(y))
        println(x.equals(z))
        println(y==z)

    } 
} 
```

**Output:**

```scala
true
false
false

```

在这里，我们使用了**等于**和 **==** 的方法来检查是否相等。