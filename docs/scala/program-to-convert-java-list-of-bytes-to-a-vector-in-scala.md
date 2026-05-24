# 在 Scala 中将 Java 字节列表转换为向量的程序

> 原文:[https://www . geeksforgeeks . org/program-to-convert-Java-bytes-list-to-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-bytes-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将 Java 字节列表转换为 Scala 中的 Vector。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会发生错误。
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

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding characters to the list
        list.add(125)
        list.add(111)

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(125, 111)

```

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

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding bytes to the list
        list.add(-102)
        list.add(-123)
        list.add(88)

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(-102, -123, 88)

```