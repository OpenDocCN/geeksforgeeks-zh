# 在 Scala 中对 Java 整数集应用 foreach()方法的程序

> 原文:[https://www . geesforgeks . org/program-to-apply-foreach-method-on-Java-set-of-integer-in-Scala/](https://www.geeksforgeeks.org/program-to-apply-foreach-method-on-java-set-of-integers-in-scala/)

方法 *foreach()* 可以通过利用 Scala 的 *JavaConversions* 对象应用于 Scala 中的 Java 整数集。此外，这里需要使用 *JavaConversions* 对象作为 **foreach** 方法在 Java 语言中是不存在的。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Program to apply foreach() method on 
// Java set of integers in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of int in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(7)
        set.add(8)
        set.add(9)

        // Applying foreach method on 
        // the set and displaying
        // output
        set.foreach(println)

    }
}
```

**Output:**

```scala
7
8
9

```

因此，当 *foreach* 方法应用于所述整数集合时，该集合的每一项都被打印。
T3】例:2#

```scala
// Program to apply foreach() method on 
// Java set of integers in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of int in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(9)
        set.add(5)
        set.add(1)

        // Applying foreach method on 
        // the set and displaying
        // output
        set.foreach(println)

    }
}
```

**Output:**

```scala
1
5
9

```

它与上面的例子相同，但是这里的元素不是以正确的顺序陈述的，但是在 Set 中，它需要以正确的顺序，所以结果输出是以正确的顺序。