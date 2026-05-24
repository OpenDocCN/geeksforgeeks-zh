# 在 Scala 中将 Java 字符列表转换为向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-characters-to-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-characters-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将 Java 字符列表转换为 Scala 中的 Vector。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会发生错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to a Vector in Scala

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
        list.add('a')
        list.add('b')

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(a, b)

```

因此，结果输出的顺序与上面列表中的顺序相同。
**例:2#**

```scala
// Scala program to convert Java list 
// to a Vector in Scala

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
        list.add('c')
        list.add('a')
        list.add('d')

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(c, a, d)

```

这里，所述字符没有按正确的顺序排列，因此结果输出也没有按正确的顺序排列。