# 对 Scala 中的 java 字符列表应用 foreach()方法的程序

> 原文:[https://www . geesforgeks . org/program-to-apply-foreach-method-on-Java-list-in-Scala/](https://www.geeksforgeeks.org/program-to-apply-foreach-method-on-java-list-of-characters-in-scala/)

方法 *foreach()* 可以通过利用 Scala 的 *JavaConversions* 对象应用于 Scala 中的 Java 字符列表。此外，这里我们需要使用 *JavaConversions* 对象作为 **foreach** 方法在 Java 语言中是不存在的。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala

// Program to apply foreach() method on 
// Java list of characters in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of characters in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('e')
        list.add('f')
        list.add('g')

        // Applying foreach method on 
        // the list and displaying
        // output
        list.foreach(println)

    }
}
```

**Output:**

```scala
e
f
g

```

因此，当对所述字符列表应用*或*方法时，列表的每一项都被打印。
T3】例:2#

```scala
// Program to apply foreach() method on 
// Java list of characters in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of characters in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('j')
        list.add('l')
        list.add('k')

        // Applying foreach method on 
        // the list and displaying
        // output
        list.foreach(println)

    }
}
```

**Output:**

```scala
j
l
k

```

它与上面的例子相同，但是这里列表的元素没有以正确的顺序出现。