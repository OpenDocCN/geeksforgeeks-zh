# 在 Scala 中将 Java 短路列表转换为向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-short-to-a-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-shorts-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将一个 Java 的 Shorts 列表转换成 Scala 中的 Vector。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作，否则将会出现错误。
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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(1000)
        list.add(999)

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(1000, 999)

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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(-1000)
        list.add(888)
        list.add(999)

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(-1000, 888, 999)

```