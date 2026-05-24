# 在 Scala 中对 Java 集应用 foreach()方法的程序

> 原文:[https://www . geesforgeks . org/program-to-apply-foreach-method-on-Java-set-in-Scala/](https://www.geeksforgeeks.org/program-to-apply-foreach-method-on-java-set-in-scala/)

方法 *foreach()* 可以利用 Scala 的 *JavaConversions* 对象应用于 Scala 中的 Java 集合。此外，这里我们需要使用 *JavaConversions* 对象作为 **foreach** 方法在 Java 语言中是不存在的。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Program to apply foreach() method on 
// Java set in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating set in Java
    val set = new java.util.HashSet[String]()

    // Adding strings to the set
    set.add("GfG")
    set.add("is a")
    set.add("CS-portal")

    // Applying foreach method on 
    // the set and displaying
    // output
    set.foreach(println)

}
}
```

**Output:**

```scala
GfG
is a
CS-portal

```

因此，当对所述器械包应用*或*方法时，器械包的每一项都被打印。
T3】例:2#

```scala
// Program to apply foreach() method on 
// Java set in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating set in Java
    val set = new java.util.HashSet[String]()

    // Adding strings to the set
    set.add("Geeks")
    set.add("CS portal")
    set.add("GfG")

    // Applying foreach method on 
    // the set and displaying
    // output
    set.foreach(println)

}
}
```

**Output:**

```scala
Geeks
GfG
CS portal

```

它与上面的例子相同，但是这里具有更多字数的集合的元素最终被打印。因此，这里不维持规定的顺序。