# 在 Scala 中的 Java 列表上应用 foreach()方法的程序

> 原文:[https://www . geesforgeks . org/program-to-apply-foreach-method-on-Java-list-in-Scala/](https://www.geeksforgeeks.org/program-to-apply-foreach-method-on-java-list-in-scala/)

方法 *foreach()* 可以利用 Scala 的 *JavaConversions* 对象应用于 Scala 中的 Java 列表。此外，这里需要使用 *JavaConversions* 对象作为 **foreach** 方法在 Java 语言中是不存在的。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Program to apply foreach() method on 
// Java List in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = java.util.Arrays.asList(7, 5, 2)

        // Applying foreach method on 
        // the list and displaying
        // output
        list.foreach(println)

    }
}
```

**Output:**

```scala
7
5
2

```

因此，当对所述列表应用*或*方法时，将打印列表的每一项。
T3】例:2#

```scala
// Program to apply foreach() method on 
// Java List in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = java.util.Arrays.asList(11, 12, 13)

        // Applying foreach method on 
        // the list and displaying
        // output
        list.foreach(println)

    }
}
```

**Output:**

```scala
11
12
13

```

它与上面的例子相同，但是这里列表的元素没有以正确的顺序出现。