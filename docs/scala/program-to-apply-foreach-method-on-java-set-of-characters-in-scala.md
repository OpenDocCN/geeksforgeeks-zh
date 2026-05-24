# 在 Scala 中对 Java 字符集应用 foreach()方法的程序

> 原文:[https://www . geesforgeks . org/program-to-apply-foreach-method-on-Java-set-characters-in-Scala/](https://www.geeksforgeeks.org/program-to-apply-foreach-method-on-java-set-of-characters-in-scala/)

方法 *foreach()* 可以通过利用 Scala 的 *JavaConversions* 对象应用于 Scala 中的 Java 字符集。此外，这里我们需要使用 *JavaConversions* 对象作为 **foreach** 方法在 Java 语言中是不存在的。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Program to apply foreach() method on 
// Java set of characters in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of Char in Java
        val set = new java.util.HashSet[Char]()

        // Adding Characters to the set
        set.add('a')
        set.add('b')
        set.add('c')

        // Applying foreach method on 
        // the set and displaying
        // output
        set.foreach(println)

    }
}
```

**Output:**

```scala
a
b
c

```

因此，当对所述字符集应用*或*方法时，会打印该组的每一项。
T3】例:2#

```scala
// Program to apply foreach() method on 
// Java set of characters in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of Char in Java
        val set = new java.util.HashSet[Char]()

        // Adding Char to the set
        set.add('d')
        set.add('c')
        set.add('b')

        // Applying foreach method on 
        // the set and displaying
        // output
        set.foreach(println)

    }
}
```

**Output:**

```scala
b
c
d

```

它与上面的例子相同，但是这里的元素不是以正确的顺序陈述的，但是在 Set 中，它需要以正确的顺序，所以结果输出是以正确的顺序。