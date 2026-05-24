# 确定 Scala 对象的类别

> 原文:[https://www . geeksforgeeks . org/确定 scala 对象的类别/](https://www.geeksforgeeks.org/determine-the-class-of-a-scala-object/)

为了确定 Scala 对象的类，我们使用 **getClass** 方法。此方法返回作为实例父类的类详细信息。
下面是确定 Scala 对象的类的例子。

**用参数调用方法–**

**示例#1:**

```scala
// Scala program to determine the class of a Scala object

// Creating object 
object Geeks
{ 
    // Using getClass method
    def printClass(num: Int*) 
    {
        println("class: " + num.getClass)
    }

    // Main method 
    def main(args: Array[String]) 
    { 
        // Calling parameter with parameter
        printClass(4, 2)
    } 
} 
```

**输出:**

```scala
class: class scala.collection.mutable.WrappedArray$ofInt
```

在上面的例子中，用参数调用 printClass 方法演示了 Scala 类。

**无参数调用方法–**

**例 2:**

```scala
// Scala program to determine the class of a Scala object

// Creating object 
object Geeks 
{ 
    // Using getClass method
    def printClass(num: Int*) 
    {
        println("class: " + num.getClass)
    }

    // Main method 
    def main(args: Array[String]) 
    { 
        // Calling method without parameter
        printClass()
    } 
} 
```

**输出:**

```scala
class: class scala.collection.immutable.Nil$
```

在上面的例子中，调用不带参数的 printClass 方法演示了 Scala 类。

**附加 get*方法–**

**示例#3:**

```scala
// Scala program to show how 
// the additional get* methods work

sealed trait Person
class Boy extends Person
class Girl extends Person

// Creating object
object Person 
{
    // factory method
    def getPerson(s: String): Person = 
        if (s == "Boy") new Boy else new Girl
}

object ObjectCastingTest extends App 
{

    val person = Person.getPerson("Boy")

    // class object_casting.Boy
    println("person: " + person.getClass)

    // object_casting.Boy
    println("person: " + person.getClass.getName)  

    // Boy
    println("person: " + person.getClass.getSimpleName)  

    // object_casting.Boy
    println("person: " + person.getClass.getCanonicalName)  

}
```

**输出:**

```scala
person: class Boy
person: Boy
person: Boy
person: Boy
```

上面的代码显示了额外的 get*方法`getName, getSimpleName,`和`getCanonicalName`是如何工作的。